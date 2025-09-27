# 📦 Desafio 6: Criação de Conta de Armazenamento no Azure – Bootcamp Microsoft Azure AZ-900

Este repositório contém meu sexto desafio do bootcamp **Microsoft Azure AZ-900**, oferecido pela **DIO em parceria com a Microsoft**.  

O objetivo deste desafio foi praticar a criação e configuração de uma **Conta de Armazenamento** no Azure, explorando também recursos adicionais como compartilhamento de arquivos, filas, tabelas, migração de dados e o uso do **AzCopy**.

## Criação da Conta de Armazenamento

### Básico
- **Assinatura:** usei a padrão.  
- **Grupo de recursos:** selecionei o grupo já criado em laboratório anterior.  
- **Nome da conta de armazenamento:** definido conforme exigência do Azure (nome único, entre 3 e 24 caracteres, apenas letras minúsculas e números).  
- **Região:** (US) East US.  
- **Desempenho:** escolhi **Standard**, pois era apenas um teste. Em cenários que exigem alta performance e baixa latência (exemplo: sistemas de pagamento instantâneo como PIX), o ideal seria **Premium**.  
- **Redundância:** optei por **LRS (Locally Redundant Storage)**, que mantém três cópias dentro do mesmo datacenter. Para produção, não seria o ideal.

### Avançado
Mantive as configurações padrão.

### Rede
Mantive as configurações padrão.

### Proteção de Dados
- **Exclusão temporária para blobs e contêineres:** desabilitada, pois não fazia sentido em ambiente de teste.  
  Em produção, ativar este recurso é essencial para evitar perda acidental de dados.  

### Criptografia
Mantive a configuração padrão (será aprofundada em laboratórios futuros).

### Marcações
Não utilizei.

## Recursos Criados Dentro da Conta

- **Compartilhamento de Arquivos (File Share):**  
  - Criei um compartilhamento chamado `tecnologia`.  
  - Mantive as configurações padrão.  
  - Após criado, é possível acessar o script de conexão para **Windows, Linux e macOS**, via protocolo SMB na porta 445.  

- **Fila (Queue):**  
  - Criada para testes de mensageria.  
  - Interessante ver na prática como o endpoint público e a URL padrão são gerados automaticamente.  

- **Tabela (Table):**  
  - Criada para armazenar dados estruturados.  

## Migrações no Azure
Explorei também o recurso de **Migrações**:
- Criei um projeto com assinatura e grupo de recursos padrão.  
- Geografia: **Brasil**.  
- Método de conectividade: **Ponto de extremidade público**.  
- Objetos de migração possíveis: servidores, bancos de dados, aplicativos web ou Data Box.  

### Exemplo com Data Box
- Tipo de transferência: **Importar para o Azure**.  
- Região de destino: **South Brazil**.  
- Opções:  
  - **Data Box Disk (35TB)**  
  - **Data Box (80TB)**  
  - **Data Box Heavy (800TB)**  
  - **Import/Export Job**  

## AzCopy
Também testei o uso da ferramenta **AzCopy**, utilizada para transferir dados entre o ambiente local e o Azure Storage.  

Passos seguidos:
1. Baixei o executável (Windows/Linux/macOS).  
2. No portal, acessei a **conta de armazenamento > contêineres > novo contêiner**.  
3. Criei um **token SAS** com permissões específicas.  
4. Copiei a **URL SAS** do blob.  
5. Usei o comando no terminal, indicando a pasta de origem e a URL SAS de destino.  


## ✅ Conclusão
Este laboratório me ajudou a entender:
- Como criar e configurar uma **conta de armazenamento no Azure**.  
- Diferenças entre redundâncias (LRS, GRS, ZRS) e quando usá-las.  
- Criação prática de **compartilhamento de arquivos, filas e tabelas**.  
- Como funciona o **processo de migração com Data Box**.  
- Transferência de arquivos com **AzCopy**.  

