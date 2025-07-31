<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Printsy</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@3.4.1/dist/tailwind.min.css" rel="stylesheet">
  <script src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js" defer></script>
</head>
<body class="bg-blue-50 text-gray-800" x-data="{ cart: [] }">

  <!-- Encabezado -->
  <header class="bg-blue-700 text-white p-5 shadow-md">
    <div class="container mx-auto flex justify-between items-center">
      <h1 class="text-3xl font-bold">Printsy</h1>
      <nav class="space-x-4">
        <a href="#" class="hover:text-gray-300">Inicio</a>
        <a href="#productos" class="hover:text-gray-300">Tazones</a>
        <a href="#galeria" class="hover:text-gray-300">Galería</a>
        <a href="#tienda" class="hover:text-gray-300">Tienda Online</a>
        <a href="#contacto" class="hover:text-gray-300">Contacto</a>
      </nav>
    </div>
  </header>

  <!-- Eslogan -->
  <section class="bg-beige-100 py-4">
    <div class="container mx-auto text-center">
      <p class="text-xl font-semibold text-blue-700">Printsy: creatividad que se disfruta taza a taza</p>
    </div>
  </section>

  <!-- Hero principal -->
  <section class="bg-blue-100 py-16">
    <div class="container mx-auto text-center px-4">
      <h2 class="text-4xl font-bold mb-4">Diseños únicos para cada ocasión</h2>
      <p class="text-lg mb-6">Personaliza tu taza o elige entre nuestros modelos exclusivos</p>
      <a href="#productos" class="bg-blue-700 text-white px-6 py-3 rounded-full hover:bg-blue-800 transition">Ver catálogo</a>
    </div>
  </section>

  <!-- Productos -->
  <section id="productos" class="container mx-auto px-4 py-16">
    <h3 class="text-2xl font-bold text-center mb-10">Nuestros Tazones</h3>
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8">
      <!-- Producto 1 -->
      <div class="bg-white shadow-md rounded-xl overflow-hidden">
        <img src="https://images.unsplash.com/photo-1560159616-3c4d80e88aa8?auto=format&fit=crop&w=600&q=80" alt="Tazón Floral" class="w-full h-60 object-cover">
        <div class="p-4">
          <h4 class="text-xl font-semibold">Tazón Floral</h4>
          <p class="text-gray-600">Perfecto para regalar o disfrutar tu café con estilo.</p>
          <p class="mt-2 font-bold">$8.990 CLP</p>
          <button @click="cart.push('Tazón Floral')" class="mt-2 w-full bg-blue-700 text-white px-4 py-2 rounded hover:bg-blue-800 transition">Agregar al Carrito</button>
        </div>
      </div>

      <!-- Producto 2 -->
      <div class="bg-white shadow-md rounded-xl overflow-hidden">
        <img src="https://images.unsplash.com/photo-1605522802957-142bcbf2b24e?auto=format&fit=crop&w=600&q=80" alt="Tazón Personalizado" class="w-full h-60 object-cover">
        <div class="p-4">
          <h4 class="text-xl font-semibold">Tazón Personalizado</h4>
          <p class="text-gray-600">Agrega tu nombre o frase favorita.</p>
          <p class="mt-2 font-bold">$10.990 CLP</p>
          <button @click="cart.push('Tazón Personalizado')" class="mt-2 w-full bg-blue-700 text-white px-4 py-2 rounded hover:bg-blue-800 transition">Agregar al Carrito</button>
        </div>
      </div>

      <!-- Producto 3 -->
      <div class="bg-white shadow-md rounded-xl overflow-hidden">
        <img src="https://images.unsplash.com/photo-1617814071499-d0b7bb7a9ae2?auto=format&fit=crop&w=600&q=80" alt="Tazón Divertido" class="w-full h-60 object-cover">
        <div class="p-4">
          <h4 class="text-xl font-semibold">Tazón Divertido</h4>
          <p class="text-gray-600">Diseños con frases motivadoras o humorísticas.</p>
          <p class="mt-2 font-bold">$7.990 CLP</p>
          <button @click="cart.push('Tazón Divertido')" class="mt-2 w-full bg-blue-700 text-white px-4 py-2 rounded hover:bg-blue-800 transition">Agregar al Carrito</button>
        </div>
      </div>
    </div>
  </section>

  <!-- Tienda Online -->
  <section id="tienda" class="container mx-auto px-4 py-16">
    <h3 class="text-2xl font-bold text-center mb-10">Compra en Línea</h3>
    <template x-if="cart.length > 0">
      <div class="bg-white p-6 rounded-lg shadow mb-10">
        <h4 class="text-xl font-semibold mb-4">Carrito de Compras</h4>
        <ul class="list-disc pl-5 mb-4">
          <template x-for="(item, index) in cart" :key="index">
            <li x-text="item"></li>
          </template>
        </ul>
        <button @click="alert('Gracias por tu compra!')" class="bg-green-500 text-white px-4 py-2 rounded hover:bg-green-600 transition">Finalizar Compra</button>
      </div>
    </template>
    <p class="text-center text-gray-500" x-show="cart.length === 0">Tu carrito está vacío</p>
  </section>

  <!-- Galería -->
  <section id="galeria" class="bg-white py-16">
    <div class="container mx-auto px-4">
      <h3 class="text-2xl font-bold text-center mb-10">Galería de Diseños</h3>
      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-6">
        <img src="https://source.unsplash.com/400x400/?mug,design" alt="taza 1" class="rounded-xl shadow-md hover:scale-105 transition-transform">
        <img src="https://source.unsplash.com/400x400/?mug,coffee" alt="taza 2" class="rounded-xl shadow-md hover:scale-105 transition-transform">
        <img src="https://source.unsplash.com/400x400/?mug,custom" alt="taza 3" class="rounded-xl shadow-md hover:scale-105 transition-transform">
        <img src="https://source.unsplash.com/400x400/?mug,gift" alt="taza 4" class="rounded-xl shadow-md hover:scale-105 transition-transform">
      </div>
    </div>
  </section>

  <!-- Contacto -->
  <section id="contacto" class="bg-blue-100 py-10">
    <div class="container mx-auto text-center">
      <h3 class="text-2xl font-bold mb-4">¿Tienes dudas o quieres un diseño personalizado?</h3>
      <p class="mb-6">Escríbenos por WhatsApp o redes sociales</p>
      <a href="https://wa.me/56912345678" class="bg-green-500 text-white px-6 py-3 rounded-full hover:bg-green-600 transition">Enviar WhatsApp</a>
    </div>
  </section>

  <!-- Footer -->
  <footer class="bg-blue-700 text-white py-6 mt-10">
    <div class="container mx-auto text-center">
      <p>&copy; 2025 Printsy. Todos los derechos reservados.</p>
      <div class="mt-2 space-x-4">
        <a href="#" class="hover:text-gray-300">Instagram</a>
        <a href="#" class="hover:text-gray-300">Facebook</a>
        <a href="#tienda" class="hover:text-gray-300">Tienda Online</a>
      </div>
    </div>
  </footer>

</body>
</html>
