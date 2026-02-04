```dataview
> TABLE WITHOUT ID
> file.link AS "Name",
> GeoParent AS "Located In",
> GeoCategory AS "Type",
> choice(GeoCategory = "Landmark", LandmarkType, 
> 	choice(GeoCategory ="Locale", GeoLocaleSubType, 
> 	choice(GeoCategory = "City", CitySubType, "N/A"))) AS "Sub-Type",
> PrimaryNPC AS "Primary NPC"
> FROM "Geography"
>> WHERE contains(Factions, this.file.link) AND dg-publish = true
> SORT GeoCategory ASC, file.name ASC
> ```