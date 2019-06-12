# NBA-database


<!DOCTYPE html>
<!-- Roman Rybak, Howard Chen - database final project -->

<html>
    <head>
        <title>Javascript - NBA Database</title>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <style>

          tr{background-color: white;}
          th{background-color: pink;}
          body { background-color: #00FFFF; } 
          body{position: fixed;}
          .tab{float: middle;}
          .tab-2{margin-top: 20px}
          .tab-2 input{margin-left: 10px}
           tr:hover{background-color:yellow;}
           header{margin-left: 600px;
           font-size: 4em; margin-top: 30px;}
           .container{background-color: #ADFF2F;
            margin-left: 500px;
            margin-top: 50px;}

           div tab-1 {color:yellow;}
        </style>
        </head>

        <header>NBA database</header>

        <body>
        
         <div class="container">
            <div class="tab tab-1">
            <table id="table" border="1">
            <tr>
                <th>Name</th>
                <th>Height</th>
                <th>Position</th>
                <th>Salary</th>
                <th>Team</th>
                <th>Team President</th>
                
            </tr>
             
            <!-- For convenience, below are provided two examples for table values, they can be modified or deleted -->

            <tr>
                <td>Gordon Hayward</td>
                <td>6 ft 8in</td>
                <td>Small forward</td>
                <td>$29,730,000</td>
                <td>Celtics</td>
                <td>Rich Gotham</td>
                
            </tr>

             <tr>
                <td>Roman Rybak</td>
                <td></td>
                <td>Small forward</td>
                <td>$29,730,000</td>
                <td>Celtics</td>
                <td>Rich Gotham</td>
                
            </tr>
          
            
            
        </table>
          </div>
            <div class="tab tab-2">
        Name: <input type="text" name="Name" id="Name" /><br/><br/>
        Height: <input type="text" name="Height" id="Height" /><br/><br/>
        Position: <input type="text" name="Position" id="Position" /><br/><br/>
        Salary: <input type="text" name="Salary" id="Salary" /><br/><br/>
        Team: <input type="text" name="Team" id="Team" /><br/><br/>
        Team_President: <input type="text" name="Team President" id="Team President" /><br/><br/>


        <button onclick="addRow();">Add Row</button><br/><br/>
        <button onclick="editHtmlTbleSelectedRow();">Edit</button>
        <button onclick="removeSelectedRow();">Remove</button>
        

        <table border="1">
        <input type="file" id="file-input" />
        <!--<h3>Contents of the file:</h3>-->
        <pre id="file-content"></pre> 

        <script>

        function readSingleFile(e) {
          var file = e.target.files[0];
        if (!file) {
          return;
  }
      var reader = new FileReader();
      reader.onload = function(e) {
      var contents = e.target.result;
      displayContents(contents);
  };
     reader.readAsText(file);
}

    function displayContents(contents) {
    var element = document.getElementById('file-content');
    element.textContent = contents;
}

    document.getElementById('file-input')
   .addEventListener('change', readSingleFile, false);

             var rIndex,
                table = document.getElementById("table");
            
          
            function checkEmptyInput()
            {
                var isEmpty = false,
                    Name = document.getElementById("Name").value,
                    Height = document.getElementById("Height").value,
                    Position = document.getElementById("Position").value;
                    Salary = document.getElementById("Salary").value;
                    Team = document.getElementById("Team").value;
                    Team_President = document.getElementById("Team President").value;
                    
            
            }

            
        function addRow(){
                
        var Name = document.getElementById('Name').value;
        var Height = document.getElementById('Height').value;
        var Position = document.getElementById('Position').value;
        var Salary = document.getElementById('Salary').value;
        var Team = document.getElementById('Team').value;
        var Team_President = document.getElementById('Team President').value;
      
                  
    
                var table = document.getElementsByTagName('table')[0];
                  
                var newRow = table.insertRow(table.rows.length);
                  
                 
                   var cel1 = newRow.insertCell(0);
                   var cel2 = newRow.insertCell(1);
                   var cel3 = newRow.insertCell(2);
                   var cel4 = newRow.insertCell(3);
                   var cel5 = newRow.insertCell(4);
                   var cel6 = newRow.insertCell(5);
                   var cel7 = newRow.insertCell(6);
                   
                  
                
                   cel1.innerHTML = Name;
                   cel2.innerHTML = Height;
                   cel3.innerHTML = Position;
                   cel4.innerHTML = Salary;
                   cel5.innerHTML = Team;
                   cel6.innerHTML = Team_President;
                   
                  }
             function selectedRowToInput()
            {
                
                for(var i = 1; i < table.rows.length; i++)
                {
                    table.rows[i].onclick = function()
                    {
                      
                      rIndex = this.rowIndex;
                      document.getElementById("Name").value = this.cells[0].innerHTML;
                      document.getElementById("Height").value = this.cells[1].innerHTML;
                      document.getElementById("Position").value = this.cells[2].innerHTML;
                      document.getElementById("Salary").value = this.cells[3].innerHTML;
                      document.getElementById("Team").value = this.cells[4].innerHTML;
                      document.getElementById("Team President").value = this.cells[5].innerHTML;
                      
                    };
                }
            }
            selectedRowToInput();
            
            function editHtmlTbleSelectedRow()
            {
                var Name = document.getElementById("Name").value,
                    Height = document.getElementById("Height").value,
                    Position = document.getElementById("Position").value;
                    Salary = document.getElementById("Salary").value;
                    Team = document.getElementById("Team").value;
                    Team_President = document.getElementById("Team President").value;
  

               if(!checkEmptyInput()){

                   table.rows[rIndex].cells[0].innerHTML = Name;
                   table.rows[rIndex].cells[1].innerHTML = Height;
                   table.rows[rIndex].cells[2].innerHTML = Position;
                   table.rows[rIndex].cells[3].innerHTML = Salary;
                   table.rows[rIndex].cells[4].innerHTML = Team;
                   table.rows[rIndex].cells[5].innerHTML = Team_President;
                   
              }
            }
            
            function removeSelectedRow()
            {
                table.deleteRow(rIndex);
                
                document.getElementById("Name").value = "";
                document.getElementById("Height").value = "";
                document.getElementById("Position").value = "";
                document.getElementById("Salary").value = "";
                document.getElementById("Team").value = "";
                document.getElementById("Team President").value = "";
                
            }
           
            

        </script>
        
   </body> 

</html>
