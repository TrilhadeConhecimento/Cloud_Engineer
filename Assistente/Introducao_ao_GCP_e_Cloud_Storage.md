
# Cloud Engineer

## Introdução ao Google Cloud Plataform (GCP):
O Google Cloud Platform (GCP) é um conjunto de serviços de computação em nuvem oferecido pelo Google. Ele fornece uma variedade de recursos, incluindo armazenamento, processamento e análise de dados, além de ferramentas para desenvolvimento de aplicativos. A GCP é conhecida por sua infraestrutura global, segurança robusta e integração com outras soluções do Google, como o Google Workspace e o YouTube. A plataforma é projetada para atender desde pequenas startups até grandes corporações, proporcionando flexibilidade, escalabilidade e economia de custos.
## Como funciona e para que é:
A GCP utiliza uma rede global de data centers para fornecer serviços de computação, armazenamento e análise de dados. Seus principais componentes incluem:
- Compute Engine: Máquinas virtuais escaláveis.
- App Engine: Plataforma para desenvolvimento e hospedagem de aplicativos.
- Kubernetes Engine: Gerenciamento de contêineres.
- Cloud Storage: Armazenamento de objetos.
- BigQuery: Análise de grandes volumes de dados.

A GCP é usada para: 
- Hospedagem de Aplicações: Web e móveis.
- Análise de Dados: Big data e machine learning.
- Armazenamento de Dados: Seguro e durável.
- Desenvolvimento de Software: Ambientes ágeis para desenvolvimento e teste.
- Esses serviços permitem inovação rápida, redução de custos e maior eficiência operacional.

## Vantagens de utilização:
- Escalabilidade: Ajuste de recursos conforme a demanda.
- Segurança: Criptografia de dados e conformidade com padrões internacionais.
- Custo-Efetividade: Pagamento por uso, reduzindo custos operacionais.
- Inovação: Acesso a tecnologias avançadas como AI e machine learning.
- Integração: Fácil integração com ferramentas Google e sistemas de terceiros.
## Exemplos:
Spotify
- Uso: Armazenamento, análise em tempo real e aprendizado de máquina.
- Benefícios: Desempenho, escalabilidade e recomendações personalizadas.
  
Coca-Cola
- Uso: Gerenciamento de dados de vendas e marketing com BigQuery.
- Benefícios: Análise de dados rápida e decisões de marketing informadas.

## Referências:
https://cloud.google.com/docs/overview?hl=pt-br

# Exemplo de uso: Introdução ao Cloud Storage

O Cloud Storage permite o armazenamento global e a recuperação de volumes de dados a qualquer momento.

É possível usar o Cloud Storage para vários cenários, como veiculação de conteúdo de sites, armazenamento de dados para arquivamento e recuperação de desastres ou distribuição de objetos de dados grandes aos usuários por download direto.

## O que é um Bucket?
Bucket é o recipiente de dados básico da plataforma do Google Cloud.  

TUDO que será armazenado no Cloud Storage precisa estar contido em um bucket.  
- Ao criar um bucket, você fornece a ele um nome exclusivo globalmente e um local geográfico em que o bucket e o conteúdo são armazenados.

## Gerenciamento de permissões
É possível usar o Identity and Access Management (IAM) para controlar o acesso a buckets individuais.
- O IAM permite conceder acesso granular a recursos específicos do Google Cloud e ajuda a impedir o acesso a outros recursos.
- Com o IAM, você gerencia o controle de acesso definindo quem (identidade) tem qual acesso (papel) a que recurso.

# Criando um bucket:
Para criar um bucket:  

- Via CONSOLE:

No console do Cloud, acesse Menu de navegação > Cloud Storage > Buckets.

Clique em "CREATE":

![Criando Bucket](https://cdn.qwiklabs.com/IzqJx37G8qJo1n9GkUrmq6QUeznWZKcpnFyIF1jK0%2Bc%3D)

- Via LINHA DE COMANDO:

gcloud config set compute/region "REGION"

gcloud config permite visualizar e editar propriedades da interface de linha de comando do Google Cloud.

O que vem depois no comando define a região do projeto (no campo REGION, insira a região desejada).


gsutil mb gs://<YOUR-BUCKET-NAME>


gsutil mb ou "make bucket" cria um bucket do Cloud Storage no camino especificado.

# Fazendo upload de dados em um bucket
![](https://cdn.qwiklabs.com/8tnHNHkj30vDqnzokQ%2FcKrxmOLoxgfaswd9nuZkEjd8%3D)
Link da imagem: https://cdn.qwiklabs.com/8tnHNHkj30vDqnzokQ%2FcKrxmOLoxgfaswd9nuZkEjd8%3D

- Via CONSOLE:
Na guia Objetos, clique em Fazer upload de arquivos e selecione a imagem salva em seu computador.

- Via LINHA DE COMANDO:

curl https://cdn.qwiklabs.com/8tnHNHkj30vDqnzokQ%2FcKrxmOLoxgfaswd9nuZkEjd8%3D --output kitten.png

O comando curl acessa a URL da imagem e a salva com o nome especificado em --output


gsutil cp kitten.png gs://YOUR-BUCKET-NAME

Já o seguinte comando faz upload da imagem no bucket

# Tornando a imagem acessível publicamente
- Clique na guia Permissões acima da lista de arquivos.

- Verifique se a visualização está definida como Principais. Clique em Conceder acesso para abrir o painel Adicionar principais.

- Na caixa Novos principais, digite allUsers.

- No menu suspenso Selecionar um papel, clique em Cloud Storage > Leitor de objetos do Storage.

- Clique em Salvar.

- Na janela Você quer mesmo tornar esse recurso público?, clique em Permitir acesso público.


gsutil acl ch -u AllUsers:R gs://YOUR-BUCKET-NAME/kitten.png

O comando acima também faz a mesma coisa: para todos os usuários (allUsers) dá a permissão de leitura (R ou Read) para a imagem do bucket.

- Para verificar, clique na guia Objetos e retorne à lista desses itens. A coluna Acesso público do objeto precisa estar definida como Público para a Internet.

- Selecione o botão Copiar URL do seu objeto e cole o link em outra guia para acessar a imagem.

# Referências
- https://www.cloudskillsboost.google/paths/36/course_templates/637/labs/464071?locale=pt_BR

- https://www.cloudskillsboost.google/paths/36/course_templates/637/labs/464070?locale=pt_BR

- https://cloud.google.com/storage/docs/buckets?hl=pt-br

- https://cloud.google.com/iam/docs/overview?hl=pt-br#:~:text=A%20principal%20can%20be%20a,is%20typically%20an%20email%20address.

- https://cloud.google.com/sdk/gcloud/reference/config
















