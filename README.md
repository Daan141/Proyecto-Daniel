# Proyecto-Daniel
Este proyecto fue diseñado en c# con el fin de desarrollar un sistema de gestión de productos del supermercado Soriana

**Objetivo del Proyecto:**

Desarrollar un sistema de gestión de productos para un supermercado que permita una administración eficiente del inventario, el seguimiento de las ventas y la optimización de la reposición de productos. Este sistema facilitará la organización y el control de los productos en el inventario, mejorará la precisión en el manejo de datos y proporcionará informes útiles para la toma de decisiones.

Características Principales:

**Gestión de Inventario:**

Registro y actualización de productos con detalles como nombre, código, categoría, precio, y cantidad disponible.
Funcionalidad para agregar, editar y eliminar productos.
Control de stock mínimo y máximo para la gestión de reposiciones automáticas.

**Registro de Ventas:**

Captura de transacciones de ventas con detalles de productos vendidos, cantidades y precios.
Generación de recibos o facturas para los clientes.
Integración con sistemas de pago y manejo de métodos de pago múltiples.

**Control de Proveedores:**

Registro de proveedores con información de contacto y detalles de productos suministrados.
Gestión de órdenes de compra y seguimiento de entregas.

**Informes y Análisis:**

Generación de informes sobre ventas, inventario, productos más vendidos y niveles de stock.
Análisis de tendencias de ventas y comportamiento de compra para la toma de decisiones estratégicas.

**Interfaz de Usuario:**

Interfaz intuitiva y fácil de usar para el personal del supermercado.
Panel de control con acceso a las funciones principales del sistema.

**Seguridad y Control de Acceso:**

Gestión de usuarios con roles y permisos específicos para garantizar la seguridad de la información.
Registro de actividades y auditorías de cambios en el sistema.

**Integración y Escalabilidad:**

Posibilidad de integrar el sistema con otros software o hardware del supermercado, como cajas registradoras o sistemas de contabilidad.
Escalabilidad para adaptarse al crecimiento del negocio y a nuevas necesidades.

**Beneficios Esperados:**

Reducción de errores en el manejo de inventario y ventas.
Mejora en la eficiencia operativa y en la toma de decisiones.
Incremento en la satisfacción del cliente mediante un manejo más preciso de los productos y servicios.

**Avance de Código**
```
using System;
using System.Collections.Generic;
using System.Linq;

namespace Supermercado
{
    // Clase para representar un producto
    public class Producto
    {
        public int Id { get; set; }
        public string Nombre { get; set; }
        public string Categoria { get; set; }
        public decimal Precio { get; set; }
        public int Cantidad { get; set; }

        public Producto(int id, string nombre, string categoria, decimal precio, int cantidad)
        {
            Id = id;
            Nombre = nombre;
            Categoria = categoria;
            Precio = precio;
            Cantidad = cantidad;
        }

        public override string ToString()
        {
            return $"ID: {Id}, Nombre: {Nombre}, Categoría: {Categoria}, Precio: {Precio:C}, Cantidad: {Cantidad}";
        }
    }

    // Clase para gestionar el inventario del supermercado
    public class Supermercado
    {
        private List<Producto> inventario = new List<Producto>();

        // Agregar un producto al inventario
        public void AgregarProducto(Producto producto)
        {
            inventario.Add(producto);
            Console.WriteLine("Producto agregado: " + producto);
        }

        // Eliminar un producto del inventario
        public void EliminarProducto(int id)
        {
            var producto = inventario.FirstOrDefault(p => p.Id == id);
            if (producto != null)
            {
                inventario.Remove(producto);
                Console.WriteLine("Producto eliminado: " + producto);
            }
            else
            {
                Console.WriteLine("Producto no encontrado.");
            }
        }

        // Listar todos los productos en el inventario
        public void ListarProductos()
        {
            Console.WriteLine("Inventario:");
            foreach (var producto in inventario)
            {
                Console.WriteLine(producto);
            }
        }

        // Buscar un producto por ID
        public void BuscarProducto(int id)
        {
            var producto = inventario.FirstOrDefault(p => p.Id == id);
            if (producto != null)
            {
                Console.WriteLine("Producto encontrado: " + producto);
            }
            else
            {
                Console.WriteLine("Producto no encontrado.");
            }
        }
    }

    // Programa principal
    class Program
    {
        static void Main(string[] args)
        {
            var supermercado = new Supermercado();

            // Agregar algunos productos
            supermercado.AgregarProducto(new Producto(1, "Manzana", "Frutas", 0.5m, 100));
            supermercado.AgregarProducto(new Producto(2, "Leche", "Lácteos", 1.2m, 50));
            supermercado.AgregarProducto(new Producto(3, "Pan", "Panadería", 0.8m, 30));

            // Listar todos los productos
            supermercado.ListarProductos();

            // Buscar un producto
            supermercado.BuscarProducto(2);

            // Eliminar un producto
            supermercado.EliminarProducto(1);

            // Listar todos los productos después de eliminar uno
            supermercado.ListarProductos();
        }
    }
}

```
![image](https://github.com/user-attachments/assets/e4d51d7a-d3c7-4b77-8cda-1fa621ddc77b)

