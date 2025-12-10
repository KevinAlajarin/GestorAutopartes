# Sistema de Gestión de Ventas de Autopartes

## 📋 Descripción
Sistema de gestión integral para comercio de autopartes desarrollado en Java. Permite administrar catálogo de productos, clientes, pedidos y ventas con control de stock y diferentes métodos de pago.

## 🎯 Características Principales

### **1. Gestión de Autopartes**
- ✅ Alta, baja y modificación de autopartes
- ✅ Control de stock y stock mínimo
- ✅ Listado de productos con stock bajo
- ✅ Modificación de stock manual

### **2. Gestión de Clientes**
- ✅ Registro y modificación de datos de clientes
- ✅ Consulta de pedidos por cliente
- ✅ Validación de ID único

### **3. Gestión de Pedidos**
- ✅ Creación de pedidos con reserva de stock
- ✅ Modificación de cantidad y estado
- ✅ Conversión de pedidos a ventas
- ✅ Estados: Reservado, Cancelado, Vendido

### **4. Gestión de Ventas**
- ✅ Venta directa de autopartes
- ✅ Venta desde pedido reservado
- ✅ Sistema de métodos de pago con descuentos y recargos
- ✅ Modificación de ventas registradas

### **5. Sistema de Pagos**
- **Efectivo**: 10% de descuento
- **Débito**: Precio total sin descuentos
- **Crédito**: Recargos según cuotas:
  - 2 cuotas: 6% recargo
  - 3 cuotas: 12% recargo
  - 6 cuotas: 20% recargo

## 🏗️ Arquitectura del Sistema

### **Estructura de Clases**
📁 clases/
├── Main.java # Punto de entrada y menú principal
├── GestorEmpresa.java # Controlador principal (lógica de negocio)
├── Autoparte.java # Modelo de producto/autoparte
├── Cliente.java # Modelo de cliente
├── Pedido.java # Modelo de pedido
├── Venta.java # Modelo de venta
└── MetodoPago.java # Modelo de método de pago

### **Diagrama de Relaciones**

Cliente (1) --- (n) Pedido
Pedido (1) --- (1) Venta
Autoparte (1) --- (n) Pedido
Autoparte (1) --- (n) Venta
Venta (1) --- (1) MetodoPago

## 📊 Modelo de Datos

### **Autoparte**
- `IdProducto` (String): Identificador único
- `Denominacion`, `Descripcion`, `Categoria`, `marca`, `Modelo` (String)
- `Precio` (float): Precio unitario
- `Stock`, `StockMinimo` (int): Control de inventario

### **Cliente**
- `idCliente` (String): Identificador único
- `nombre`, `apellido`, `direccion` (String)
- `telefono` (int)

### **Pedido**
- `idPedido` (String): Identificador único
- `cantidad` (int): Cantidad solicitada
- `total` (float): Precio total
- `estado` (String): "Reservado", "Cancelado", "Vendido"
- `idCliente`, `idProducto` (String): Referencias

### **Venta**
- `idVenta` (String): Identificador único
- `metodoPago` (String): "debito", "credito", "efectivo"
- `precioTotal` (float): Total después de descuentos/recargos
- `idPedido` (String): Referencia opcional si viene de pedido
- `cantidad` (int)
- `idCliente`, `idProducto` (String): Referencias

## 🚀 Instalación y Ejecución

### **Requisitos Previos**
- Java JDK 8 o superior
- IDE Java (Eclipse, IntelliJ, NetBeans) o línea de comandos

### **Pasos para Ejecutar**

1. **Clonar/Descargar el proyecto**
   ```bash
   # Descargar el proyecto
   git clone <repositorio>
   # O descargar el archivo .rar y descomprimir
