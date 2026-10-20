# calidad-cartera-banca-chile


# Calidad de cartera de la banca chilena (2019–2026)

**¿Qué bancos y carteras se deterioraron más, cuándo, y qué lo explica?**

Proyecto de análisis de datos con información pública de la CMF y del Banco Central de Chile.

## Pregunta de negocio
1. ¿Qué bancos y qué carteras (consumo, comerciales, vivienda) se deterioraron más que el sistema bancario?
2. ¿La morosidad de consumo reacciona al desempleo y a la tasa de interés? ¿Con cuántos meses de rezago?
3. ¿Los bancos más deteriorados estaban más o menos provisionados que el resto?

## Por qué importa
Una gerencia de riesgo de crédito necesita saber qué segmentos se están deteriorando y si las provisiones acompañan ese deterioro, para decidir apetito de riesgo, políticas de cobranza y niveles de cobertura.

## Hipótesis (a contrastar, pueden resultar falsas)
- **H1:** la mora de consumo sube con un rezago de 3 a 9 meses tras un aumento del desempleo.
- **H2:** los bancos orientados a consumo y retail se deterioraron más que los bancos grandes después de 2022.
- **H3:** en los bancos más deteriorados, la cobertura de provisiones no creció al mismo ritmo que la mora.

## Datos
| Fuente | Contenido | Frecuencia |
|---|---|---|
| CMF – Indicadores de cartera vencida | % de cartera vencida por banco y tipo de cartera | Trimestral (mar, jun, sep, dic), 2019–2026 |
| CMF – Índices de provisiones de riesgo de crédito | Provisiones/colocaciones por banco, cartera y categoría de riesgo | Trimestral, 2019–2026 |
| Banco Central de Chile (BDE) | Desempleo y tasa de política monetaria | Mensual |

Los archivos originales se guardan sin modificar en `raw/`. Los datos CMF son provisorios y pueden ser corregidos por la CMF.

## Metodología (plan)
1. Descarga y registro de fuentes (`docs/control_descargas.md`).
2. Limpieza y modelo de datos: tabla larga banco–período–cartera–indicador (`clean/`).
3. Base SQL y consultas de análisis.
4. Estadística: correlaciones con rezago y regresión simple.
5. Visualización en Power BI y memo ejecutivo.

## Estructura del repositorio
- `raw/`: archivos originales descargados
- `clean/`: datos limpios y base de datos
- `docs/`: decisiones de limpieza, diccionario de datos, control de descargas

## Limitaciones conocidas
- Los indicadores son porcentajes agregados por banco, no datos de clientes.
- Bancos pequeños y sucursales extranjeras tienen carteras reducidas, así que sus porcentajes son volátiles.
- La fusión Banco Bice–Security (1 nov 2025) y el cambio de nombre de Itaú Corpbanca a Banco Itaú Chile requieren tratamiento especial.
- Hay valores no disponibles ("---") cuyo tratamiento se documenta en `docs/decisiones.md`.

## Uso de IA
Se usó Claude como apoyo para diseñar el plan del proyecto y revisar ideas. El análisis, la limpieza y la interpretación son del autor.

## Hallazgos
_Pendiente. Se completará al finalizar el análisis._

## Autor
Eduardo Sotomayor · Ingeniería Civil, Universidad de Concepción · [LinkedIn](https://www.linkedin.com/in/TU-USUARIO)

**Estado:** en desarrollo, iniciado el 19 de octubre de 2026.
