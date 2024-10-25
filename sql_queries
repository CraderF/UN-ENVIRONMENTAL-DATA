# mySQL queries 

USE UN_DATA;
SHOW TABLES;

SELECT * FROM co2emissionest;
SELECT * FROM land;
SELECT * FROM threatened_species;

DROP TABLE IF EXISTS global_co2emissions;
CREATE TABLE global_co2emissions
	SELECT 'Total, all countries or areas' AS `Country/Region`, year, Series AS 'Series', SUM(Value) AS total_emissions 
	FROM co2emissionest
    WHERE Series = 'Emissions (thousand metric tons of carbon dioxide)'
    GROUP BY year;
SELECT * FROM global_co2emissions;


DROP TABLE IF EXISTS global_threatened_species;
CREATE TABLE global_threatened_species
	SELECT 'Total, all countries or areas' AS `Country/Region`, year, Series AS 'Series', SUM(Value) AS total_threatened_species 
	FROM threatened_species
    WHERE Series = 'Threatened Species: Total (number)'
    GROUP BY year;
SELECT * FROM global_threatened_species;


DROP TABLE IF EXISTS global_forest_cover;
CREATE TABLE global_forest_cover
	SELECT 'Total, all countries or areas' AS `Country/Region`, year, Series AS 'Series', value
	FROM land
    WHERE Series = 'Forest cover (thousand hectares)' AND `Country/Region` = 'Total, all countries or areas';
SELECT * FROM global_forest_cover;


DROP TABLE IF EXISTS global_permanent_crops;
CREATE TABLE global_permanent_crops
	SELECT 'Total, all countries or areas' AS `Country/Region`, year, Series AS 'Series', value
	FROM land
    WHERE Series = 'Permanent crops (thousand hectares)' AND `Country/Region` = 'Total, all countries or areas';
SELECT * FROM global_permanent_crops;


DROP TABLE IF EXISTS joined_co2_ts;
CREATE TABLE joined_co2_ts AS
	SELECT co2.`Country/Region` AS 'CO2 Country/Region', co2.year AS 'CO2 Year', co2.Series AS 'CO2 Series', co2.total_emissions AS 'CO2 Value',
           ts.`Country/Region` AS 'TS Country/Region', ts.year AS 'TS Year', ts.Series AS 'TS Series', ts.total_threatened_species AS 'TS Value'
	FROM global_co2emissions co2
	LEFT JOIN global_threatened_species ts
	ON co2.year = ts.year 
	AND co2.`Country/Region` = ts.`Country/Region`
	
	UNION
	
	SELECT co2.`Country/Region` AS 'CO2 Country/Region', co2.year AS 'CO2 Year', co2.Series AS 'CO2 Series', co2.total_emissions AS 'CO2 Value',
           ts.`Country/Region` AS 'TS Country/Region', ts.year AS 'TS Year', ts.Series AS 'TS Series', ts.total_threatened_species AS 'TS Value'
	FROM global_threatened_species ts
	LEFT JOIN global_co2emissions co2
	ON ts.year = co2.year 
	AND ts.`Country/Region` = co2.`Country/Region`;

SELECT * FROM joined_co2_ts;

DROP TABLE IF EXISTS joined_co2_fc;
CREATE TABLE joined_co2_fc AS 
	SELECT co2.`Country/Region` AS 'CO2 Country/Region', co2.year AS 'CO2 Year', co2.Series AS 'CO2 Series', co2.total_emissions AS 'CO2 Value',
    fc.`Country/Region` AS 'FC Country/Region', fc.year AS 'FC Year', fc.Series AS 'FC Series', fc.value AS 'FC Value'
    FROM global_co2emissions co2
    LEFT JOIN global_forest_cover fc
    ON co2.year = fc.year
    AND co2.`Country/Region` = fc.`Country/Region`
    
    UNION
    
    SELECT co2.`Country/Region` AS 'CO2 Country/Region', co2.year AS 'CO2 Year', co2.Series AS 'CO2 Series', co2.total_emissions AS 'CO2 Value',
    fc.`Country/Region` AS 'FC Country/Region', fc.year AS 'FC Year', fc.Series AS 'FC Series', fc.value AS 'FC Value'
    FROM global_forest_cover fc
    LEFT JOIN global_co2emissions co2
    ON fc.year = co2.year
    AND fc.`Country/Region` = co2.`Country/Region`;

SELECT * FROM joined_co2_fc;

DROP TABLE IF EXISTS joined_ts_pc;
CREATE TABLE joined_ts_pc AS 
	SELECT ts.`Country/Region` AS 'TS Country/Region', ts.year AS 'TS Year', ts.Series AS 'TS Series', ts.total_threatened_species AS 'TS Value',
		   pc.`Country/Region` AS 'PC Country/Region', pc.year AS 'PC Year', pc.Series AS 'PC Series', pc.value AS 'PC Value'
	FROM global_threatened_species ts
    LEFT JOIN global_permanent_crops pc
    ON ts.year = pc.year
    AND ts.`Country/Region` = pc.`Country/Region`
    
    UNION
    
    SELECT ts.`Country/Region` AS 'TS Country/Region', ts.year AS 'TS Year', ts.Series AS 'TS Series', ts.total_threatened_species AS 'TS Value',
		   pc.`Country/Region` AS 'PC Country/Region', pc.year AS 'PC Year', pc.Series AS 'PC Series', pc.value AS 'PC Value'
	FROM global_permanent_crops pc
    LEFT JOIN global_threatened_species ts
    ON pc.year = ts.year
    AND pc.`Country/Region` = ts.`Country/Region`;

SELECT * FROM joined_ts_pc;

DROP TABLE IF EXISTS joined_ts_fc;
CREATE TABLE joined_ts_fc AS 
	SELECT ts.`Country/Region` AS 'TS Country/Region', ts.year AS 'TS Year', ts.Series AS 'TS Series', ts.total_threatened_species AS 'TS Value',
    fc.`Country/Region` AS 'FC Country/Region', fc.year AS 'FC Year', fc.Series AS 'FC Series', fc.value AS 'FC Value'
    FROM global_threatened_species ts
    LEFT JOIN global_forest_cover fc
    ON ts.year = fc.year
    AND ts.`Country/Region` = fc.`Country/Region`
    
    UNION
    
    SELECT ts.`Country/Region` AS 'TS Country/Region', ts.year AS 'TS Year', ts.Series AS 'TS Series', ts.total_threatened_species AS 'TS Value',
    fc.`Country/Region` AS 'FC Country/Region', fc.year AS 'FC Year', fc.Series AS 'FC Series', fc.value AS 'FC Value'
    FROM global_forest_cover fc
    LEFT JOIN global_threatened_species ts
    ON fc.year = ts.year
    AND fc.`Country/Region` = ts.`Country/Region`;

SELECT * FROM joined_ts_fc;
