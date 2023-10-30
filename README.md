CREATE TABLE especies (
    id INT PRIMARY KEY,
    nome VARCHAR(50)
);

INSERT INTO especies (id, nome) VALUES
(1, 'gato'),
(2, 'cachorro'),
(3, 'pássaro');

CREATE TABLE animais (
    id INT PRIMARY KEY,
    nome VARCHAR(50),
    especie_id INT,
    peso DECIMAL(5, 2),
    cor VARCHAR(20),
    altura DECIMAL(5, 2),
    observacao TEXT,
    data_nascimento DATE
);

INSERT INTO animais (id, nome, especie_id, peso, cor, data_nascimento)
VALUES
(1, 'Pluto', 2, 20, 'preto', '2009-05-10'),
(2, 'Garfield', 1, 15, 'laranja', '2014-09-20'),
(3, 'Tom', 1, 12, 'cinza', '2003-07-15'),
(4, 'Pateta', 2, 25, 'preto', '2008-09-05'),
(5, 'Tweety', 3, 0.1, 'amarelo', '2019-07-27');

ALTER TABLE animais
DROP COLUMN cor;

ALTER TABLE animais
ALTER COLUMN nome drop default;

DELETE FROM animais
WHERE especie IN ('gato', 'cachorro');

ALTER TABLE animais
DROP COLUMN data_nascimento;

DELETE FROM animais;

DROP TABLE especies;
