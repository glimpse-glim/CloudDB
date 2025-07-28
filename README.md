# CloudDB:
A npm **CloudDB**, feito de fs e Path, construído em javascript, é uma opção fácil e alternativa aos bancos de dados comuns.

# Glimpse:

![CloudDB Em Parceria com a glimpse](https://i.postimg.cc/dVk3SKvd/24-Sem-T-tulo-20250728184409.png)

Uma Empresa virtual de tecnologia crescendo a **Glimpse** é a melhor alternativas para desenvolvedores.

# Instalação:

```
npm i @glimpse/cloudDB
```
# Modo de Uso:

Aqui contém todas as funções da CloudDB, **seu modo de uso, e exemplos práticos**
```
import { CloudDB } from '@glimpse/cloudDB';

// Criando a instância do banco
const db = new CloudDB('meubanco.json', {
  mode: 'json',        // modo banco de dados
  autoSave: true       // salva sempre que você muda algo
});

// Inicializa o banco (cria o arquivo e carrega os dados)
await db.init();
console.log('📁 Banco de dados inicializado');

// Salvando dados
await db.set('glim', { idade: 14, role: 'criador da Glimpse' });
await db.set('parguin', { idade: 15, role: 'dev explorador' });
await db.set('mensagem', 'Bem-vindo à Glimpse!');
console.log('✅ Dados inseridos');

// Buscando dados
const glim = await db.get('glim');
console.log('🔍 Dados de Glim:', glim);

// Verificando se uma chave existe
const temLucas = await db.has('lucas');
console.log('❓ Tem "lucas"?', temLucas ? 'Sim' : 'Não');

// Listando todas as chaves
const chaves = await db.keys();
console.log('🗝️ Chaves do banco:', chaves);

// Pegando todos os valores
const valores = await db.values();
console.log('📦 Valores salvos:', valores);

// Tamanho do banco
const tamanho = await db.size();
console.log('📐 Quantidade de registros:', tamanho);

// Deletando um dado
await db.delete('parguin');
console.log('❌ Parguin removido');

// Mostrando tudo o que sobrou
console.log('📄 Tudo no banco:', await db.all());

// Limpando o banco completamente
await db.clear();
console.log('⚠️ Banco limpo:', await db.all());

// Adicionando algo novo (teste final)
await db.set('backup', { status: 'ok' });

// Salvando manualmente (caso autoSave: false)
await db.save();
console.log('💾 Salvo manualmente');

// Mostrando o JSON puro
console.log('📑 JSON bruto:', db.toJSON());

// Caminho completo do arquivo salvo
console.log('📂 Arquivo salvo em:', db.getPath());

// Recarregando o banco do arquivo
await db.reload();
console.log('🔄 Recarregado do disco:', await db.all());```

