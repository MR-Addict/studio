<main class="w-full animate-slideFromBottom md:animate-slideFromLeft">
  <table>
    <thead>
      <tr class="h-10">
        <th>镜像</th>
        <th>时间</th>
        <th>大小</th>
        <th>状态</th>
        <th>资源</th>
      </tr>
    </thead>
    <tbody>
      {#each { length: 20 } as item}
        <tr class="border border-gray-300 dark:border-gray-500 p-5 rounded-xl h-10">
          <td data-cell="镜像"><div class="skeleton" /></td>
          <td data-cell="时间"><div class="skeleton" /></td>
          <td data-cell="大小"><div class="skeleton" /></td>
          <td data-cell="状态"><div class="skeleton" /></td>
          <td data-cell="资源"><div class="skeleton" /></td>
        </tr>
      {/each}
    </tbody>
  </table>
</main>

<style lang="postcss">
  table {
    @apply w-full;
  }
  table tr {
    @apply text-left border border-gray-300 dark:border-gray-500;
  }
  table :is(th, td) {
    @apply p-2 whitespace-nowrap;
  }

  @media (min-width: 769px) {
    table tbody tr:nth-of-type(even) {
      background-size: 200% 100%;
      background-position-x: 180%;
      animation: 2s pulse ease-in-out infinite;
      @apply dark:from-light dark:via-dark/50 dark:to-light;
      @apply bg-gradient-to-r from-gray-200 from-40% via-gray-300/60 via-50% to-gray-200 to-60%;
    }
  }

  @media (max-width: 768px) {
    table thead {
      @apply hidden;
    }
    table td {
      padding: 0.25rem;
      display: grid;
      grid-template-columns: 5ch auto;
    }
    table td::before {
      content: attr(data-cell);
    }
    .skeleton {
      background-size: 200% 100%;
      background-position-x: 180%;
      animation: 2s pulse ease-in-out infinite;
      @apply dark:from-light dark:via-dark/50 dark:to-light;
      @apply bg-gradient-to-r from-gray-200 from-40% via-gray-300/60 via-50% to-gray-200 to-60%;
    }
  }

  @keyframes pulse {
    to {
      background-position-x: -20%;
    }
  }
</style>
