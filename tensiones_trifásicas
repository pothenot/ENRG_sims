import numpy as np
import matplotlib.pyplot as plt

# Parámetros
f = 50  # Frecuencia de la red (Hz)
phi = 1.107149611  # Fase
w = 2 * np.pi * f  # Velocidad angular
sec = 1.05  # Espira
B = 1  # Teslas
Em = B * w * sec  # Tensión máxima

# Vector de tiempo
t = np.arange(0, 60e-3, 0.0001)

# Tensiones trifásicas
l1 = Em * np.cos(2 * np.pi * f * t)  # Fase R
l2 = Em * np.cos(2 * np.pi * f * t - 120 / 360 * 2 * np.pi)  # Fase S
l3 = Em * np.cos(2 * np.pi * f * t - 240 / 360 * 2 * np.pi)  # Fase T
ref = np.zeros_like(t)  # Línea de referencia

# Seleccionar un rango de datos para graficar
x_vector = slice(200, 400)

# Graficar tensiones trifásicas
plt.figure(figsize=(8, 5))
plt.plot(l1[x_vector], 'b', label='Fase R')
plt.plot(l2[x_vector], 'r', label='Fase S')
plt.plot(l3[x_vector], 'g', label='Fase T')
plt.plot(ref[x_vector], 'k')

# Configurar el eje X
plt.xticks([0, 50, 100, 150, 200], ['0', 'π/2', 'π', '3π/2', '2π'])
plt.xlim([0, 200])
plt.grid(True, linestyle='--', alpha=0.6)
plt.legend()
plt.title('Tensiones trifásicas instantáneas')
plt.xlabel('Tiempo')
plt.ylabel('Tensión (V)')
plt.show()

# Suma de tensiones trifásicas
plt.figure(figsize=(8, 5))
plt.plot(l1[x_vector] + l2[x_vector] + l3[x_vector], 'b', label='Suma de Fases')
plt.axhline(0, color='k', linestyle='--')
plt.legend()
plt.title('Suma de Tensiones Trifásicas')
plt.xlabel('Tiempo')
plt.ylabel('Tensión (V)')
plt.grid(True, linestyle='--', alpha=0.6)
plt.show()
