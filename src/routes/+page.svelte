<script>
  import { fromJSON } from 'postcss';

  const age = 23;

  const list = [
    'Guilherme',
    'Alex Nascimento',
    'Léo Zion',
  ];

  const listObj = [
    {name: 'Guilherme', age: '35'},
    {name: 'Alex Nascimento', age: '29'},
    {name: 'Léo Zion', age: '43'},
  ];
</script>

<h1>MyApp</h1>

{#if age > 20 && age < 30 }
  <p>Idade esta entre 20 e 30 anos</p>
{:else}
  <p>Idade esta fora dos parametros</p>
{/if}

{#each list as item}
  <p>{item}</p>
{/each}

{#each listObj as {name, age}}
  <p>{name} tem {age} anos</p>
{/each}