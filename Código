CREATE DATABASE UniversidadUAN;

USE UniversidadUAN;

CREATE TABLE Estudiante(
	codigo INT UNIQUE PRIMARY KEY auto_increment,
    nombre VARCHAR(50) NOT NULL,
    apellido VARCHAR(50) NOT NULL,
    promedio DECIMAL(3,2) NOT NULL
);

CREATE TABLE Curso(
	codigo INT UNIQUE PRIMARY KEY auto_increment,
    departamento ENUM('Matematicas','Fisica','Sistemas','Biologia') NOT NULL,
    nombre VARCHAR(50) NOT NULL,
    creditos INT NOT NULL,
    nota DECIMAL(3,2) NOT NULL
);

CREATE TABLE RegistrarNotas(
	id_registro INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
	estudiante_codigo INT NOT NULL,
    curso_codigo INT NOT NULL,
    nota DECIMAL (3,2) NOT NULL CHECK(nota BETWEEN 1.5 AND 5),
    FOREIGN KEY (estudiante_codigo) REFERENCES Estudiante(codigo),
    FOREIGN KEY (curso_codigo) REFERENCES Curso(codigo)   
);

INSERT INTO Estudiante (nombre, apellido, promedio)
VALUES
	('Juanita','Perez',0),
    ('Andres','Martinez',0),
    ('Alberto','Gomez',0),
    ('Isabella','Murillo',0);
    
INSERT INTO Curso(departamento, nombre, creditos, nota)
VALUES
	('Matemáticas','Matematicas Discretas',3,0),
    ('Física','Electromecánica',4,0),
    ('Sistemas','TGS',3,0),
    ('Biología','Anatomia',2,0);

INSERT INTO RegistrarNotas(estudiante_codigo, curso_codigo, nota)
VALUES
	(1,4,2.50),
	(2,3,4.25),
	(3,2,3.50),
	(4,1,4.75);
    
SELECT * FROM RegistrarNotas;

CREATE INDEX idx_nombre_estudiante ON Estudiante(nombre);
CREATE INDEX idx_apellido_estudiante ON Estudiante(apellido);

CREATE INDEX idx_departamento_curso ON Curso(departamento);
CREATE INDEX idx_nombre_curso ON Curso(nombre);
CREATE INDEX idx_creditos_curso ON Curso(creditos);

CREATE INDEX idx_estudiante_codigo_notas ON RegistrarNotas(estudiante_codigo);
CREATE INDEX idx_curso_codigo_notas ON  RegistrarNotas(curso_codigo);
CREATE INDEX idx_nota_notas ON RegistrarNotas(nota);
