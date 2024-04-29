<script>
    let showTable1 = false;
    let showTable2 = false;
  
    function toggleTable1() {
      showTable1 = !showTable1;
    }
  
    function toggleTable2() {
      showTable2 = !showTable2;
    }
  </script>
  
  <nav class="bg-gray-800">
    <ul class="flex">
      <li class="mr-6">
        <a href="/" class="text-white hover:text-gray-400 cursor-pointer" on:click={toggleTable1}>
          Elemento 1
        </a>
        {#if showTable1}
          <div class="bg-white p-4">
            <h3 class="text-lg font-bold mb-2">Tabla de Contenido 1</h3>
            <ul>
              <li>Contenido 1.1</li>
              <li>Contenido 1.2</li>
              <li>Contenido 1.3</li>
            </ul>
          </div>
        {/if}
      </li>
      <li class="mr-6">
        <a href="/" class="text-white hover:text-gray-400 cursor-pointer" on:click={toggleTable2}>
          Elemento 2
        </a>
        {#if showTable2}
          <div class="bg-white p-4">
            <h3 class="text-lg font-bold mb-2">Tabla de Contenido 2</h3>
            <ul>
              <li>Contenido 2.1</li>
              <li>Contenido 2.2</li>
              <li>Contenido 2.3</li>
            </ul>
          </div>
        {/if}
      </li>
    </ul>
  </nav>