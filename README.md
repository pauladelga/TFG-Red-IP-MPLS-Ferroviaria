# TFG-Red-IP-MPLS-Ferroviaria
# Validación de Arquitectura IP/MPLS para Entorno Ferroviario 🚄

Este repositorio contiene los archivos de configuración correspondientes al entorno de simulación del Trabajo de Fin de Grado (TFG) para el diseño de la red troncal de telecomunicaciones del tren México-Toluca.

## Arquitectura del Laboratorio

La red ha sido emulada utilizando **GNS3** con imágenes de **Cisco IOS (c7200)**. La arquitectura se divide en:
* **Underlay:** enrutamiento base mediante **OSPFv2**.
* **Transporte MPLS:** conmutación rápida mediante etiquetas con **LDP**.
* **Overlay (VPN):** segmentación de servicios críticos (Señalización) y no críticos (CCTV) mediante **VRFs** y **MP-BGP**.

## Archivos de Configuración

En este repositorio se encuentran las configuraciones extraídas (`show running-config`) de los 6 nodos de la red:
* `Acc-Via1.txt`: nodo de acceso en Vía 1 (PE).
* `Acc-Via2.txt`: nodo de acceso en Vía 2 (PE).
* `Dist-Lerma.txt` y `Dist-SantaFe.txt`: nodos de distribución (P).
* `Core-Obs.txt` y `Core-Tol.txt`: nodos del núcleo troncal (P).

## Pruebas Realizadas
Las configuraciones incluidas garantizan:
1.  **Aislamiento ciberseguro:** 100% de éxito en comunicación intra-VRF y bloqueo total inter-VRF.
2.  **Alta Disponibilidad:** convergencia sin pérdida de paquetes (*hitless failover*) mediante ECMP ante caídas de enlaces de fibra.
