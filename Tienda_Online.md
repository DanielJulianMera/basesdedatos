// Use DBML to define your database structure
// Docs: https://dbml.dbdiagram.io/docs

Table Cliente {
  Id integer [primary key]
  Nombre varchar
  Direccion varchar
  Correo_Electronico varchar
}

Table Producto {
  Id integer [primary key]
  Nombre varchar
  Precio integer
  Descripcion text
  Categoria_Id integer
  Proveedor_Id integer
}

Table Orden {
  Id integer [primary key]
  Fecha_De_Orden date
  Cliente_Id integer
}

Table Categoria {
  Id integer [primary key]
  Nombre varchar
  Direccion varchar
  Correo_Electronico varchar
}

Table Proveedor {
  Id integer [primary key]
  Nombre varchar
  Direccion varchar
  Correo_Electronico varchar
}

Table Resena {
  Id integer [primary key]
  Cliente_Id varchar
  Producto_Id varchar
  Puntuacion integer
  Comentario text
}

Ref: Categoria.Id > Producto.Categoria_Id // one-to-many                
Ref: Proveedor.Id > Producto.Proveedor_Id // one-to-many
Ref: Cliente.Id > Orden.Cliente_Id // one-to-many
Ref: Cliente.Id > Resena.Cliente_Id // one-to-many
Ref: Producto.Id > Resena.Producto_Id // one-to-many