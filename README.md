# Programa-Python-Maryury_Camacho
#Solución Problema 3 - Fase 5 Fundamentos de Programación.

def calcular_cantidad_a_pedir(stock_actual: int, stock_minimo: int) -> int:
    """Calcula la cantidad exacta a solicitar para un articulo."""
    if stock_actual < stock_minimo:
        cantidad_pedir = stock_minimo - stock_actual
    else:
        cantidad_pedir = 0
    return cantidad_pedir


def mostrar_reporte_reabastecimiento(inventario: list) -> None:
    """Recorre el inventario y muestra el nombre y cantidad a pedir por articulo."""
    print("=== REPORTE DE REABASTECIMIENTO DE INVENTARIO ===")
    for articulo in inventario:
        # Formato de fila: [codigo, nombre, stock_actual, stock_minimo]
        nombre_articulo = articulo[1]
        stock_actual = articulo[2]
        stock_minimo = articulo[3]

        cantidad_pedir = calcular_cantidad_a_pedir(stock_actual, stock_minimo)
        print(f"Articulo: {nombre_articulo} | Cantidad a pedir: {cantidad_pedir}")


def main() -> None:
   
    inventario = [
        ["ART-001", "Teclado mecanico", 4, 10],
        ["ART-002", "Mouse inalambrico", 15, 12],
        ["ART-003", "Monitor 24 pulgadas", 8, 8],
        ["ART-004", "Cable HDMI", 3, 20],
        ["ART-005", "Disco SSD 1TB", 6, 10],
        ["ART-006", "Base refrigerante", 14, 10],
    ]

    mostrar_reporte_reabastecimiento(inventario)


if __name__ == "__main__":
    main()
