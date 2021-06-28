<template>
<div class="container">
  <table class="content-table">
        <thead>
        <tr>
            <th>Titel</th>
            <th>Afbeelding</th>
            <th>Uitgever</th>
            <th>Leeftijd</th>
            <th>ISBN</th>
            <th>Publicatie</th>
            <th>Acties</th>
        </tr>
        </thead>
        <tbody>
            <tr>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Main_Image">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
            </tr>
                 <tr>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Main_Image">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
            </tr>
                 <tr>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Main_Image">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
            </tr>
                 <tr>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Main_Image">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
            </tr>
                 <tr>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Main_Image">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
                <td data-col-title="Title">Test</td>
            </tr>
        </tbody>
    </table>
    </div>
</template>

<script>
export default {

}
</script>

<style lang='scss' scoped>
.container {
   display: flex;
  justify-content: center;

  .title {
    width: 100%;
  }

.content-table {
    border-collapse: collapse;
    font-size: 1.8rem;
    width: 85%;
    border-radius: 0.5rem 0.5rem 0 0;
    overflow: hidden;
    box-shadow: $shadow-light;

    thead tr {
        background-color: #03023B;
        color: #ffffff;
        text-align: left;
        font-weight: bold;
    }

    th, td {
        padding: 1.2rem 1.5rem;
    }

    td:last-child {
        text-align: right;
    }

    th:last-child {
        text-align: center;
    }

    tbody tr {
        border-bottom: 0.1rem solid #dddddd;

        &:hover {
            color: $active-text;
        }
    }

    tbody tr:nth-of-type(even) {
        background-color: #f3f3f3;
    }

    tbody tr:last-of-type {
        border-bottom: 0.2rem solid #03023B;

        &:hover {
            background-color: rgba(182, 182, 182, 0.07);
        }
    }

    .table-image {
        width: 5.5rem;
        height: 5.5rem;
        object-fit:scale-down;
    }
}
}


@media only screen and (max-width: 600px) {

    .content-table {

        thead {
            display: none;
        }

        tr, td {
            display: block;
        }

        th:last-child {
            text-align: left;
        }

        tr:not(:last-child) {
            border-bottom: 0.2rem solid #dddddd;
        }

        td {
            padding-left: 34%;
            position: relative;
            border-bottom: 0.1rem solid #dddddd;
        }

        td:before {
            position: absolute;
            padding: 1.2rem 1.5rem;
            left: 0;
            top: 0;
            bottom: 0;
            width: 30%;
            content: attr(data-col-title);
            border-collapse: collapse;
            background-color: $color-sidebar-background-primary;
            color: #ffffff;
            font-weight: bold;
        }

    }
}


</style>