<script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.16.6/xlsx.full.min.js"></script>
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
<script>
    $(document).ready(function () {
        ExportToExcel('xlsx');
        
        function ExportToExcel(type) {
            var elt = document.getElementById('tbl_exporttable_to_xls');
            var wb = XLSX.utils.table_to_book(elt, { sheet: "sheet1" });
            var currentDate = new Date();
            var day = currentDate.getDate().toString().padStart(2, '0');
            var month = (currentDate.getMonth() + 1).toString().padStart(2, '0');
            var year = currentDate.getFullYear();
            var formattedDate = day + '-' + month + '-' + year;
            var fileName = 'All-Medicine (' + formattedDate + ').xlsx';

            // You can use the return statement as needed for your application.
            // If you want to trigger a download, use 'XLSX.writeFile'.
            // If you want to generate a base64 string, use 'XLSX.write'.

            // For example, to trigger a download:
            XLSX.writeFile(wb, fileName);
            window.close();
        }
    });
</script>
