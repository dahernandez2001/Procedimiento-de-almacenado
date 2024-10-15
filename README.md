# CREACION DEL PROCEDIMIENTO DE ALMACENADO

DELIMITER: Cambia el delimitador temporalmente de ; a $$ para que MySQL no interprete las líneas dentro del procedimiento como el final de la instrucción.
DELIMITER $$


# Define el procedimiento almacenado con el nombre "InsertarArrendamiento".
CREATE PROCEDURE InsertarArrendamiento(
    IN p_usuario VARCHAR(40),
    IN p_calificacion VARCHAR(20),
    IN p_fecha DATE,
    IN p_metodos_de_pago INT,
    IN p_correo_de_recuperacion VARCHAR(50),
    IN p_clave VARCHAR(16)
)


# BEGIN Y END: Define el bloque de código donde se ejecutan las operaciones dentro del procedimiento almacenado.
BEGIN
    
    INSERT INTO Arrendamiento (usuario, calificacion, fecha, metodos_de_pago, correo_de_recuperacion, clave)
    VALUES (p_usuario, p_calificacion, p_fecha, p_metodos_de_pago, p_correo_de_recuperacion, p_clave);
END$$

# Comprobación
Después de ejecutar el procedimiento, puedes verificar si el registro se ha insertado correctamente con una consulta simple:

SELECT * FROM Arrendamiento;

Este procedimiento es útil porque se puede llamarlo repetidamente con diferentes valores para insertar nuevos registros en la tabla tabla sin tener que escribir la consulta completa cada vez.
