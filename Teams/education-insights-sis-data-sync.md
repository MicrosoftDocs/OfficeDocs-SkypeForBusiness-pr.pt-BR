---
title: Sincronizar dados do SIS (Sistema de Informações do Aluno) com o Education Insights
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Sincronizar dados do SIS (Sistema de Informações do Aluno) com o Education Insights no Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0403e2e804397249dfd07eb03843e6b0b38653c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102117"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>Sincronizar dados do SIS (Sistema de Informações do Aluno) com o Education Insights
Quanto mais dados são alimentadas no [Education Insights](class-insights.md), os melhores professores podem dar suporte a seus alunos e os líderes de educação podem dar suporte aos professores.

Para fornecer informações no nível da organização, precisamos usar o [School Data Sync (SDS)](/SchoolDataSync) para se conectar ao SIS (Sistema de Informações do Aluno) de forma que o Insights tenha  estrutura hierárquica do sistema educacional mapeado corretamente. 

Exibir o Insights em nível de classe como o educador da classe *não* requer essa sincronização porque usamos a estrutura e as permissões de classe do Teams.

## <a name="plan-your-sis-integration"></a>Planejar a integração com o SIS
Os dados do SIS fornece a estrutura hierárquica do sistema educacional e mapeia onde o usuário será atribuído.

O insights funciona melhor ao usar o [formato do aquivo SDS V2](/schooldatasync/sds-v2-csv-file-format), mas também dá suporte ao [formato de arquivo SDS V1](/schooldatasync/school-data-sync-format-csv-files-for-sds) com *funcionalidade* limitada.

### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Diferenças entre os formatos de arquivo SDS V1 e V2

| Tipo de dados |   V1 | V2 (recomendado para os novos clientes) |
|:--- |:--- |:--- |
| **Usuários** | O formato V1 contém **apenas professores**; portanto, para definir permissões no nível da organização para os líderes de educação, você precisa pesquisá-los e definir manualmente a permissão de cada um deles. | O formato V2 contém **todas as** para que você possa atribuir permissões baseadas em função. |
| **Orgs** | O formato V1 contém **apenas escolas**, para que você veja apenas um nível de agregação (todas as suas escolas). Você pode ampliar uma escola específica usando uma lista simples, mas essa lista pode ter um grande número de escolas ou pode conter diferentes tipos de escolas que são difíceis de comparar (como a principal para a escola secundária ou ciências para a escola de arte).<br/><br/> Quando há uma hierarquia in-loco, você pode criar níveis que façam sentido, como um departamento de ciência ou arte.| O formato V2 contém **a hierarquia completa do seu distrito ou instituição**, incluindo universidades, faculdades, faculdades, campi, regiões, programas e assim por diante.<br/><br/> Com uma hierarquia, você pode ver uma agregação relevante por cada nível da hierarquia, comparar rapidamente entre unidades organizacionais em cada nível, atribuir permissão a níveis específicos, definir metas por nível da organização e assim por diante.|

### <a name="type-of-data-required"></a>Tipo de dados necessários
A tabela a seguir fornece o tipo de dados necessário para obter o melhor de Ideias.

| Tipo de dados | Exemplos do que você precisa fornecer|Por que isso é importante?|
|:--- |:--- |:--- |
| **Usuários** |   Função (como aluno)<br/> [Nível de série/Ano ](#supported-grade-level-values)(como 10)<br/> Organização (nome) | Quando atribuímos corretamente a cada pessoa sua função, nível/ano e organização, podemos garantir que os resumos e as agregação estão corretos.|
| **Orgs** | Tipo de organização (como faculdade) |   A hierarquia é importante. Por exemplo, as escolas podem pertencer a um distrito e esse distrito pode pertencer a um estado.<br/> Quando um líder de educação do distrito tem permissão para ver os dados, ele só é para as escolas nesse distrito.|
| **Aulas** | Título (como Ciência da computação 101) | Esta tabela detalha quais aulas são ministradas na organização. Esta tabela deve ser mapeada corretamente para que possamos designar o aluno para a classe correta. |
| **Inscrição** | Função (como aluno) | Esta tabela é para alunos e educadores e nos permite saber em que turma eles estão matriculados. |

> [!NOTE]
> Durante o processo de implantação, você pode decidir se deseja usar o SDS para provisionar usuários e classes em Equipes ou usá-lo somente para fornecer dados para informações.

## <a name="best-practices"></a>Práticas recomendadas
O mapeamento preciso da hierarquia e onde todos pertencem nessa hierarquia permite que o Insights forneça dados corretos e informações mais precisas e relevantes para os diferentes tipos de líderes de educação.

Quanto mais detalhes você fornecer aqui, melhores e mais relevantes serão os relatórios e destaques.
Aqui estão algumas práticas recomendadas para garantir a implantação tranquila do SDS para que seus usuários façam o melhor uso do Insights.

### <a name="users"></a>Usuários
*   Certifique *que todos os usuários* estão listados nos arquivos que você fornece e sincroniza. Isso inclui todos os alunos e funcionários que precisam ver dados das unidades organizacionais que abrangem.

    Se você tiver apenas educadores listados no SIS, adicione os outros usuários manualmente antes de carregar os arquivos para o SIS e sincronizar os dados.

    Se alguns alunos estão ausentes, as estatísticas coletadas por Ideias são apenas de alunos registrados, e isso poderá tornar os dados e as conclusão um erro.
    
*   Não deixe de *nome e sobrenome de cada*. Caso não sejam, elas são referenciadas por seu endereço de email e isso fornece uma experiência menos positiva em relatórios e destaques (cartões com informações sobre a atividade ou o desempenho do aluno).

*   O *de ano/ano deve ser entrada como 2 dígitos* (por exemplo, 07 para Ano 7). Confira a lista [mapeamento](#supported-grade-level-values). 

*   É importante adicionar o nível *ano/série a todos os alunos* para que um nível de notas/ano possa filtrar os dados.    

*   Certifique-se *atribuir a cada usuário suas unidades organizacionais relevantes*. Dessa forma, não mostraremos dados que estão induzir os dados em destaque com base em dados agregados para cada unidade.

    *   Um aluno pode ser associado a mais de uma unidade organizacional, por exemplo, alunos registrados em um programa especial ou duas docentes. Nesse caso, forneça duas linhas no arquivo de usuários para o aluno, uma para cada organização.
    
    *   Com base na unidade organizacional da equipe, você poderá definir as permissões relevantes. Certifique-se de que eles estão associados ao nível de unidade correto para que recebam as permissões de que precisam. Por exemplo, um valor atribuído a quatro escolas precisa ver todas as classes nestas escolas; um diretor precisa ver todas as classes na escola. 
    
*   A função é essencial. Embora esta lista esteja fechada, tente combinar a função [da lista](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) com a função real de cada usuário que você carregar. Dessa forma, você pode atribuir permissões baseadas em função de acordo. Por exemplo, forneça permissões para que todos os diretores vejam as classes na escola ou para que todos os professores vejam seus respectivos docentes. 

### <a name="organizations"></a>Organizações

* Não deixe de *a hierarquia real da sua organização*. Para fazer isso, adicione o arquivo manualmente. Em alguns casos, essa hierarquia não é refletida no SIS. Ainda assim, pode ser necessário aqui ver a agregação relevante por cada nível da hierarquia, atribuir permissão a níveis específicos, definir metas por nível da organização e assim por diante. 

* Verifique se *unidades da organização na árvore organizacional incluem alunos ou classes* agregar dados de alunos para eles. Recomendamos que os alunos estão no ramificação mais abaixo da árvore.

> [!NOTE]
> Para obter mais detalhes sobre a implantação do SDS, visite [planejamento da SDS](/schooldatasync/planning-school-data-sync).

## <a name="integrate-sis-using-sds"></a>Integrar o SIS usando SDS

O School Data Sync (SDS) é fornecido com o Office 365 educacional. A SDS lê os dados do SIS (Sistema de Informações do Aluno) de uma instituição de ensino e os integra com as Equipes para habilitar a criação automática de salas de aula e usuários online.

Ele também sincroniza os dados SIS com ideias.

### <a name="sync-with-insights"></a>Sincronizar com Ideias

Em primeiro lugar, você precisa ativar a alternância de Ideias para iniciar o processo de sincronização.

* No [**portal SDS**](https://sds.microsoft.com), vá para **Configurações**, role para baixo até **Coletar dados para Insights** e verifique se está ativado (é *ativado* por padrão).

* Role para baixo até a próxima opção, **Sincronizar dados organizacionais do SDS (visualização)** e ativar.

Se você não vir *opção para sincronizar dados organizacionais do SDS (visualização)* na página Configurações, vá para [página de inscrever-se do](https://aka.ms/insights/join) para fornecer suas informações e um membro da equipe falará com você.

:::image type="content" source="media/insights-sds-settings.png" alt-text="Sincronizar com botões de alternância de ideias":::

### <a name="deploy-sds"></a>Implantar SDS
**Se você já usa o SDS**, recomendamos que siga nossas [práticas recomendadas](#best-practices). 

Para sincronizar seus perfis atuais com Insights, vá para seu(s) **Perfil(s) de Sincronização**, clique em **Editar** e selecione **Sincronizar com Insights**. Para a sincronização inicial, recomendamos aguardar 24 horas para que os relatórios sejam disponibilizados após a atualização dos dados do seu SIS.  

:::image type="content" source="media/insights-sds-profile-sync.png" alt-text="Sincronizar perfil com botões de alternância do Insights":::

**Se você ainda não usa a SDS**, agora precisa [implantá-la](/schooldatasync/deploying-school-data-sync).

Durante o processo de implantação, você pode decidir se deseja usar o SDS para provisionar usuários e classes em Equipes ou usá-lo somente para fornecer dados para informações.

> [!NOTE]
> Se esse for o meio do ano e você já tiver criado equipes manualmente, use a SDS apenas para fornecer os dados para ideias. No próximo ano, considere usar a SDS para provisionar usuários e classes em Equipes também.

### <a name="verify-the-sync-process"></a>Verificar o processo de sincronização
Uma nova área de status aparece ao lado de Sincronizar dados organizacionais do SDS (visualização) na página Configurações.
 
*   Se o status for **Em andamento**, aguarde até 24 horas após a implantação do perfil SDS.

*   Se o status for **concluído**,parabéns, você poderá ver Ideias no nível da organização e seguir para a próxima etapa.

*   Se o status for **Concluído com erros**, **Concluído com avisos** ou **anulado**, baixe o arquivo de log que contém os erros e os avisos para a sincronização mais recente e verifique se você pode corrigir esses erros. 

> [!IMPORTANT]
> Se você tiver problemas, a [atendimento ao cliente](https://aka.ms/edusupport) você estiver lá para ajudá-lo.

## <a name="supported-grade-level-values"></a>Valores de nível de notas com suporte

Nos arquivos SDS, nível de série/ano definido como valores Enumerados, o que significa que você só pode fornecer um conjunto selecionado de valores dentro do arquivo CSV. Qualquer coisa diferente dos valores especificados resultará em um erro durante o processamento de sincronização.

> [!NOTE]
> O *de ano/ano deve ser entrada como 2 dígitos* (por exemplo, 07 para Ano 7).

A seção abaixo define os valores suportados no arquivo de usuários.

### <a name="united-states--worldwide-grade-levels"></a>Estados Unidos/níveis de classificação em todo o mundo
|Valor no arquivo (Coluna de nota) | Rótulo no Insights|
|:---|:---| 
|TI|Infantil|
|PR|Pré escola|
|PK|Pré-jardim de infância|
|TK|Jardim de Infância Transicional|
|KG|Jardim da infância|
|01|Primeiro ano|
|02|Segundo ano|
|03|Terceiro ano|
|04|Quarto ano|
|05|Quinto ano|
|06|Sexto ano|
|07|Sétimo ano|
|08|Oitavo ano|
|09|Nono ano|
|10|Décimo ano|
|11|Décimo primeiro ano|
|12|Decimo segundo ano|
|PS|Pós-secundário|
|PS1|Calouro pós-secundário|
|PS2|2º ano pós-secundário|
|PS3|Júnior pós-secundário|
|PS4|Sénior pós-secundário|
|estudante universitário|Estudante universitário|
|graduado|Graduado|
|pós-graduação|Pós-graduação (graduação com ênfase em pesquisa)|
|ex-alunos|Ex-alunos|
|adultEducation|Adult Education|
|UG|Sem nota|
|Outros|Outros|

### <a name="united-kingdom-year-groups"></a>Grupos de anos do Reino Unido
|Valor no arquivo (Coluna de nota) | Rótulo no Insights|
|:---|:---| 
|TI|Berçário|
|PR|Pré escola|
|PK|Recepção|
|01|Ano 1|
|02|Ano 2|
|03|Ano 3|
|04|Ano 4|
|05|Ano 5|
|06|Ano 6|
|07|Ano 7|
|08|Ano 8|
|09|Ano 9|
|10|Ano 10|
|11|Ano 11|
|12|Ano 12|
|13|Ano 13|
|PS|Pós-secundário|
|PS1|Pós-ensino médio, Ano 1|
|PS2|Pós-ensino médio, Ano 2|
|PS3|Pós-ensino médio, Ano 3|
|PS4|Pós-ensino médio, Ano 4|
|estudante universitário|Estudante universitário|
|graduado|Graduado|
|pós-graduação|Pós-graduação (graduação com ênfase em pesquisa)|
|ex-alunos|Ex-alunos|
|adultEducation|Adult Education|
|UG|Sem nota|
|Outros|Outros|