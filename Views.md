# sql-bootcamp-week09

# Catálogo de Vistas — TechStore

## Categoría: Básicas

### v_active_products
- **Propósito:** lista productos disponibles ocultando `cost`.
- **Tablas base:** `products`.
- **Actualizable:** SÍ (sin agregaciones, sin JOIN).
- **Uso:** frontend, búsquedas, dropdowns.

### v_valued_inventory
- **Propósito:** productos con valor monetario del stock.
- **Tablas base:** `products JOIN categories`.
- **Actualizable:** NO (tiene JOIN).
- **Uso:** reporte de inventario para finanzas.

### v_active_customers
- **Propósito:** clientes activos.
- **Actualizable:** SÍ.
- **Uso:** newsletters, listas de email.

### v_full_sales
- **Propósito:** ventas con cliente, producto y totales calculados.
- **Tablas base:** `sales JOIN customers JOIN products`.
- **Actualizable:** NO.
- **Uso:** cualquier reporte de ventas.

### v_sales_by_month
- **Propósito:** revenue agregado por mes.
- **Actualizable:** NO (GROUP BY).
- **Uso:** dashboards mensuales.

## Categoría: Avanzadas

### v_products_metrics
- **Propósito:** productos con sus métricas de venta y margen.
- **Actualizable:** NO.
- **Uso:** análisis de portafolio.

### v_customers_stats
- **Propósito:** cada cliente con sus métricas agregadas.
- **Actualizable:** NO.
- **Uso:** segmentación, marketing.

### v_vip_customers
- **Propósito:** clientes que cumplen criterio de VIP (gastado > 1000 + 3+ compras).
- **Tablas base:** `v_customers_stats`.
- **Actualizable:** NO.
- **Uso:** programa de fidelidad.

### v_low_stock_products
- **Propósito:** alerta de reposición.
- **Actualizable:** SÍ.
- **Uso:** equipo de compras.

### v_top_products
- **Propósito:** top 20 productos por revenue.
- **Actualizable:** NO (GROUP BY + ORDER BY + LIMIT).
- **Uso:** dashboards comerciales.

## Categoría: Seguridad

### v_public_catalog
- **Propósito:** catálogo expuesto sin información sensible (cost, stock exacto).
- **Tablas base:** `products JOIN categories`.
- **Actualizable:** NO.
- **Uso:** API pública del sitio web.

### v_executive_report
- **Propósito:** métricas de alto nivel para el CEO.
- **Tablas base:** múltiples (subqueries).
- **Actualizable:** NO.
- **Uso:** dashboard ejecutivo, presentaciones a inversionistas.

## Dependencias
