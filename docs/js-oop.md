Javascript
Create and compute
Compute a codice fiscale given:

Name (String)
Surname (String)
Gender (String) ["M","F"]
Birthday day (Number)
Birthday month (Number)
Birthday year (Number)
Place of birth (String)
Province of birth (String)
var cf = new CodiceFiscale({
    name: "Enzo",
    surname: "Righi",
    gender: "M",
    day: 24,
    month: 7,
    year: 1957,
    birthplace: "Napoli", 
    birthplaceProvincia: "NA" // Optional
});
console.log(cf);
Support foreign countries
Use the italian name of the foreign country (e.g. Francia, for France) as birthplace and "EE" as birthplace_provincia

var cf = new CodiceFiscale({
    name: "Enzo",
    surname: "Righi",
    gender: "M",
    day: 24,
    month: 7,
    year: 1957,
    birthplace: "Francia", 
    birthplaceProvincia: "EE"
});
console.log(cf);
Inverse Computation
Get a person data for a given Codice Fiscale. Throws an exeption if the code provided as argument is invalid.

var cf = new CodiceFiscale("RGHNZE10L24F839E");
console.log(cf.toJSON());
/** 
 OUTPUT
{
    name: "NZE",
    surname: "RGH",
    gender: "M",
    day: 24,
    month: 7,
    year:  2010,
    birthplace: "NAPOLI",
    birthplaceProvincia: "NA"
}
*/
Or you can access reversed attribute via instance properties:

var cf = new CodiceFiscale("RGHNZE10L24F839E");
console.log(cf.toJSON());
cf.name === "NZE"; // true
cf.surname === "RGH"; // true
cf.gender === "M"; // true
cf.day === 24; // true
cf.month === 7; // true
cf.year ===  2010; // true
cf.birthday === new Date(2010, 6, 24,0,0,0,0); // true
cf.birthplace === "NAPOLI"; // true
cf.birthplaceProvincia === "NA"; // true
Omocodie
Get all the omocodie for a given Codice Fiscale. It returns an array of strings

var cf = new CodiceFiscale("VNDLDL10A01G410Z");
var omocodie = cf.omocodie();