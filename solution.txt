------------------------------------------------------------
1. Create Database and connect to it
------------------------------------------------------------
psql --username=freecodecamp --dbname=postgres;

CREATE DATABASE universe;

\c universe

------------------------------------------------------------
2. Create tables as required conditions
------------------------------------------------------------
CREATE TABLE galaxy (
    galaxy_id SERIAL NOT NULL,
    star_id INTEGER  NOT NULL
    name VARCHAR(20) UNIQUE NOT NULL,
    area INTEGER,
    volume INTEGER,
    age NUMERIC,
    material TEXT,
    has_life BOOLEAN,
    has_water BOOLEAN,
);

CREATE TABLE star (
    star_id SERIAL NOT NULL,
    galaxy_id INTEGER NOT NULL,
    planet_id INTEGER NOT NULL
    name VARCHAR(20) UNIQUE NOT NULL,
    area INTEGER,
    volume INTEGER,
    age NUMERIC,
    material TEXT,
    has_life BOOLEAN,
    has_water BOOLEAN,
);

CREATE TABLE planet (
    planet_id SERIAL NOT NULL,
    star_id INTEGER  NOT NULL,
    moon_id INTEGER  NOT NULL,
    name VARCHAR(20) UNIQUE NOT NULL,
    area INTEGER,
    volume INTEGER,
    age NUMERIC,
    material TEXT,
    has_life BOOLEAN,
    has_water BOOLEAN
);

CREATE TABLE moon (
    moon_id SERIAL NOT NULL,
    planet_id INTEGER NOT NULL,
    name VARCHAR(20) UNIQUE NOT NULL,
    area INTEGER,
    volume INTEGER,
    age NUMERIC,
    material TEXT,
    has_life BOOLEAN,
    has_water BOOLEAN,
);

CREATE TABLE more_info (
    more_info_id SERIAL NOT NULL,
    object_id INTEGER,
    name VARCHAR(20) UNIQUE NOT NULL,
    description TEXT
);

------------------------------------------------------------
3. Fill the tables as required data conditions
------------------------------------------------------------
INSERT INTO galaxy VALUES 
(1, 1, 'galaxy1', 500, 750, 1500.75, 'solid', true, true),
(2, 2, 'galaxy2', 500, 750, 1500.75, 'solid', true, true),
(3, 3, 'galaxy3', 500, 750, 1500.75, 'solid', true, true),
(4, 4, 'galaxy4', 500, 750, 1500.75, 'solid', true, true),
(5, 5, 'galaxy5', 500, 750, 1500.75, 'solid', true, true),
(6, 6, 'galaxy6', 500, 750, 1500.75, 'solid', true, true);

INSERT INTO star VALUES
(1, 1, 1, 'star1', 500, 750, 1500.75, 'solid', true, true),
(2, 2, 2, 'star2', 500, 750, 1500.75, 'solid', true, true),
(3, 3, 3, 'star3', 500, 750, 1500.75, 'solid', true, true),
(4, 4, 4, 'star4', 500, 750, 1500.75, 'solid', true, true),
(5, 5, 5, 'star5', 500, 750, 1500.75, 'solid', true, true),
(6, 6, 6, 'star6', 500, 750, 1500.75, 'solid', true, true);

INSERT INTO planet VALUES
(1,  1,  1, 'planet1', 500, 750, 1500.75, 'solid', true, true),
(2,  2,  2, 'planet2', 500, 750, 1500.75, 'solid', true, true),
(3,  3,  3, 'planet3', 500, 750, 1500.75, 'solid', true, true),
(4,  4,  4, 'planet4', 500, 750, 1500.75, 'solid', true, true),
(5,  5,  5, 'planet5', 500, 750, 1500.75, 'solid', true, true),
(6,  6,  6, 'planet6', 500, 750, 1500.75, 'solid', true, true),
(7,  6,  7, 'planet7', 500, 750, 1500.75, 'solid', true, true),
(8,  6,  8, 'planet8', 500, 750, 1500.75, 'solid', true, true),
(9,  6,  9, 'planet9', 500, 750, 1500.75, 'solid', true, true),
(10, 6, 10, 'planet10', 500, 750, 1500.75, 'solid', true, true),
(11, 6, 11, 'planet11', 500, 750, 1500.75, 'solid', true, true),
(12, 6, 12, 'planet12', 500, 750, 1500.75, 'solid', true, true);

INSERT INTO moon VALUES 
(1,   1, 'moon1', 500, 750, 1500.75, 'solid', true, true),
(2,   2, 'moon2', 500, 750, 1500.75, 'solid', true, true),
(3,   3, 'moon3', 500, 750, 1500.75, 'solid', true, true),
(4,   4, 'moon4', 500, 750, 1500.75, 'solid', true, true),
(5,   5, 'moon5', 500, 750, 1500.75, 'solid', true, true),
(6,   6, 'moon6', 500, 750, 1500.75, 'solid', true, true),
(7,   7, 'moon7', 500, 750, 1500.75, 'solid', true, true),
(8,   8, 'moon8', 500, 750, 1500.75, 'solid', true, true),
(9,   9, 'moon9', 500, 750, 1500.75, 'solid', true, true),
(10, 10, 'moon10', 500, 750, 1500.75, 'solid', true, true),
(11, 11, 'moon11', 500, 750, 1500.75, 'solid', true, true),
(12, 11, 'moon12', 500, 750, 1500.75, 'solid', true, true),
(13, 11, 'moon13', 500, 750, 1500.75, 'solid', true, true),
(14, 11, 'moon14', 500, 750, 1500.75, 'solid', true, true),
(15, 11, 'moon15', 500, 750, 1500.75, 'solid', true, true),
(16, 11, 'moon16', 500, 750, 1500.75, 'solid', true, true),
(17, 11, 'moon17', 500, 750, 1500.75, 'solid', true, true),
(18, 11, 'moon18', 500, 750, 1500.75, 'solid', true, true),
(19, 11, 'moon19', 500, 750, 1500.75, 'solid', true, true),
(20, 11, 'moon20', 500, 750, 1500.75, 'solid', true, true);

INSERT INTO more_info VALUES
(1, 1, 'info1', 'lorem impsum'),
(2, 2, 'info2', 'lorem impsum'),
(3, 3, 'info3', 'lorem impsum'),
(4, 4, 'info4', 'lorem impsum'),
(5, 5, 'info5', 'lorem impsum');

------------------------------------------------------------
4. Primary Key and Foreign Key assignment
------------------------------------------------------------
ALTER TABLE galaxy    ADD PRIMARY KEY (galaxy_id)
ALTER TABLE star      ADD PRIMARY KEY (star_id)
ALTER TABLE planet    ADD PRIMARY KEY (planet_id)
ALTER TABLE moon      ADD PRIMARY KEY (moon_id)
ALTER TABLE more_info ADD PRIMARY KEY (more_info_id)

ALTER TABLE galaxy ADD FOREIGN KEY (star_id)   REFERENCES star   (star_id)
ALTER TABLE star   ADD FOREIGN KEY (galaxy_id) REFERENCES galaxy (galaxy_id)
ALTER TABLE star   ADD FOREIGN KEY (planet_id) REFERENCES planet (planet_id)
ALTER TABLE planet ADD FOREIGN KEY (star_id)   REFERENCES star   (star_id)
ALTER TABLE planet ADD FOREIGN KEY (moon_id)   REFERENCES moon   (moon_id)
ALTER TABLE moon   ADD FOREIGN KEY (planet_id) REFERENCES planet (planet_id)

------------------------------------------------------------
5. Compact sql db queries into universe.sql file
------------------------------------------------------------
pg_dump -cC --inserts -U freecodecamp universe > universe.sql
