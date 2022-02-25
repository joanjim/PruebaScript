let saludo = 'EJERCICIO SCRIPT:';
console.log(saludo);

const XLSX = require('xlsx');
function leerexcel(ruta){
    const workbook = XLSX.readFile(ruta);
    const workbookSheets = workbook.SheetNames;
    //console.log(workbookSheets); //Muestra las pestañas del excel
    const sheet = workbookSheets[1];
    const dataexcel = XLSX.utils.sheet_to_json(workbook.Sheets[sheet]);
    console.log(dataexcel); //Trae todos los datos

    /*for (const itemFila of dataexcel){
        console.log(itemFila['ESTADO']);
        console.log(itemFila['TOTAL']);
    }*/

    console.log("\n- El estado más afectado es: California debido al número acumulado " + "\npor muertes que es del 61526 en ese estado según los resultados.");
    console.log("\n- Resultados: Al agrupar respectivamente todas las ciudades y/o" + "\npueblos por su estado, se obtuvieron mayor cantidad de muertos en" + "\ncalifornia a diferencia de otros estados y además es uno de los 5" + "\nestados con mayor población de Estados Unidos.");
    
}

leerexcel('Co2.xlsx');