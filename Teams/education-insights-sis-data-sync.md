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
ms.openlocfilehash: 9b0d9ae3788be09e4a66724e6122791a91b6879f
ms.sourcegitcommit: 35ee6946b6f560a268d1313bf51c3cc94d8d52f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52997730"
---
# <a name="sync-student-information-system-sis-data-with-education-insights"></a>Sincronizar dados do SIS (Sistema de Informações do Aluno) com o Education Insights
Quanto mais dados são alimentadas no [Education Insights](class-insights.md), os melhores professores podem dar suporte a seus alunos e os líderes de educação podem dar suporte aos professores.

Para fornecer informações no nível da organização, precisamos usar o [School Data Sync (SDS)](/SchoolDataSync) para se conectar ao SIS (Sistema de Informações do Aluno) de forma que o Insights tenha  estrutura hierárquica do sistema educacional mapeado corretamente. 

Exibir o Insights em nível de classe como o educador da classe *não* requer essa sincronização porque usamos a estrutura e as permissões de classe do Teams.

## <a name="plan-your-school-data-sync-integration"></a>Planejar sua Integração do School Data Sync
O Microsoft School Data Sync (também conhecido como SDS) fornece os dados do Sistema de Informações Escolares (também conhecido como SIS) e sua estrutura hierárquica do sistema educacional e mapeia onde o usuário foi atribuído, bem como fornece dados adicionais sobre o aluno e a hierarquia organizacional.

O Insights funciona melhor ao usar o [formato de arquivo SDS V2](/schooldatasync/sds-v2-csv-file-format) ou superior, mas também oferece suporte ao [formato de arquivo SDS V1](/schooldatasync/school-data-sync-format-csv-files-for-sds) *com funcionalidade limitada*.


### <a name="differences-between-sds-v1-and-v2-file-formats"></a>Diferenças entre os formatos de arquivo SDS V1 e V2

Para obter o máximo dos insights, é recomendável usar o formato de arquivo v2 ou v2.1 (em breve)

| Tipo de dados | V1 | V2 |
|:--- |:--- |:--- |
| **Usuários**  | O formato V1 contém **apenas educadores**, portanto, para definir as permissões de nível organizacional para seus líderes educacionais, você precisará definir a permissão de cada um manualmente. | O formato V2 contém **todas as** para que você possa atribuir permissões baseadas em função. |
| **Orgs** | O formato V1 contém **apenas escolas**, para que você veja apenas um nível de agregação (todas as suas escolas). Você pode ampliar uma escola específica usando uma lista simples, mas essa lista pode ter um grande número de escolas ou pode conter diferentes tipos de escolas que são difíceis de comparar (como a principal para a escola secundária ou ciências para a escola de arte).<br/><br/> Quando há uma hierarquia in-loco, você pode criar níveis que façam sentido, como um departamento de ciência ou arte.| O formato V2 contém **a hierarquia completa do seu distrito ou instituição**, incluindo universidades, faculdades, faculdades, campi, regiões, programas e assim por diante.<br/><br/> Com uma hierarquia, você pode ver uma agregação relevante por cada nível da hierarquia, comparar rapidamente entre unidades organizacionais em cada nível, atribuir permissão a níveis específicos, definir metas por nível da organização e assim por diante.|

> [!NOTE]
> Os clientes não poderão utilizar o formato de arquivo integrado v2 a partir de 15 de julho de 2021, e precisarão utilizar o formato v2.1. Todas as atualizações futuras e novas funcionalidades serão feitas no formato v2.1 e ele será totalmente compatível com o formato de arquivo v1.

## <a name="best-practices"></a>Práticas recomendadas
O mapeamento preciso da hierarquia e onde todos pertencem nessa hierarquia permite que o Insights forneça dados corretos e informações mais precisas e relevantes para os diferentes tipos de líderes de educação.

Quanto mais detalhes você fornecer, melhores e mais relevantes serão os relatórios e destaques.

Aqui estão algumas práticas recomendadas para garantir a implantação tranquila do SDS para que seus usuários façam o melhor uso do Insights.

### <a name="file-format-version-to-ue"></a>Versão do formato de arquivo para ue
*   Use o formato de arquivo V2.1 (em breve) e sincronize os dados opcionais usados pelo Insights para Educação

### <a name="users-and-roles"></a>Usuários e funções
*   Certifique-se de que **todos os usuários estejam listados nos arquivos** que você fornece e sincroniza. Isso inclui todos os alunos e a equipe que precisa ver os dados das unidades organizacionais que abrangem.
    Se você atualmente tem apenas educadores listados no SIS, adicione os outros usuários manualmente antes de carregar os arquivos para o SDS e sincronizar os dados.
    As estatísticas coletadas pela Insights são apenas dos alunos inscritos, se alguns alunos estiverem ausentes, isso fará com que os dados e conclusões estejam incorretos.
    
*   Certifique-se de **fornecer o nome e o sobrenome de cada usuário**. Caso contrário, eles serão referenciados pelo seu endereço de email, e isso fornece uma experiência menos positiva nos relatórios e destaques (cartões com Insights sobre a atividade ou desempenho do aluno).

*   O nível de nota/ano deve ser baseado nesta [lista de mapeamento](#supported-grade-level-values). 

*   É importante **adicionar o nível do ano/grau para todos os alunos** para que os dados da atividade possam ser agregados e filtrados por ele.    

*   Certifique-se **atribuir a cada usuário sua unidade organizacional relevantes**. Dessa forma, o Insights para Educação não mostrará dados enganosos nos seus destaques.

    *   Um aluno pode estar associado a mais de uma unidade organizacional, por exemplo, alunos que estão matriculados em um programa especial ou duas faculdades. Caso o aluno possua mais de uma unidade organizacional, forneça uma linha para cada no arquivo de usuários daquele aluno.
    
    *   O administrador de TI pode conceder permissões com base na unidade organizacional da equipe. **Certifique-se de que os membros da equipe estejam associados ao nível de unidade correto**, para que recebam as permissões de que precisam. Por exemplo, um conselheiro atribuído para quatro escolas precisa ver todas as notas nessas escolas; um diretor precisa ver todas as turmas da sua escola. 
    
*   **A função é essencial**. Embora esta lista esteja fechada, tente combinar a função da [lista](/schooldatasync/sds-v2-csv-file-format#enumerated-values-enum-supported) com a função real de cada usuário que você carregar. Isto permitirá que você atribua de acordo com as permissões baseadas em funções. Por exemplo, forneça permissões para que todos os diretores vejam as classes na escola ou para que todos os professores vejam seus respectivos docentes. 

### <a name="organizations"></a>Organizações

* Certifique-se de **refletir a hierarquia real e completa da sua organização**. Para fazer isso, adicione o arquivo manualmente. Em alguns casos, essa hierarquia não é refletida no SIS. Ainda assim, pode ser necessário  para ver a agregação relevante de cada nível da hierarquia, atribuir permissões para níveis específicos, definir metas por nível de organização e assim por diante. 

* Certifique-se de que **todas as unidades organizacionais na árvore organizacional incluam alunos ou classes** para agregar os dados dos alunos para eles. Recomendamos que os alunos estão no ramificação mais abaixo da árvore.

> [!NOTE]
> Para obter mais detalhes sobre a implantação do SDS, visite [planejamento da SDS](/schooldatasync/planning-school-data-sync).

## <a name="integrate-sis-data-using-sds"></a>Integrar os dados do SIS usando o SDS

O School Data Sync (SDS) é fornecido com o Office 365 educacional. O SDS lê os dados do Sistema de Informação do Aluno (SIS) de uma instituição educacional e os integra com aplicativos da Microsoft, como o Teams, para permitir a criação automática de salas de aula e usuários online.

Ele também sincroniza os dados do SIS com o Insights.

Como administrador de TI, você pode escolher usar o SDS apenas para provisionamento, apenas Insights ou para ambos.

Para sincronizar suas informações do SIS com o Insights para Educação, siga as instruções em [Como implantar o SDS para o Insights](/schooldatasync/how-to-deploy-sds-for-insights).

### <a name="deploy-sds"></a>Implantar SDS
**Se você já usa o SDS**, recomendamos que siga nossas [práticas recomendadas](#best-practices). 

**Se você ainda não usa a SDS**, agora precisará [implantá-la](/schooldatasync/deploying-school-data-sync).

Durante o processo de implantação, você pode decidir se deseja usar o SDS para provisionar usuários e classes para o Teams ou usá-lo apenas para fornecer hierarquia organizacional e de usuário para o Insights também.

> [!NOTE]
> Se estiver na metade do ano e você já criou as equipes manualmente, use o SDS apenas para fornecer os dados da hierarquia organizacional e do usuário para o Insights e, no próximo ano, considere usar o SDS para provisionar usuários e classes para o Teams também.

### <a name="verify-the-sync-process"></a>Verificar o processo de sincronização
Para verificar o andamento do status da sincronização, siga as instruções em [SDS para Integridade de Dados do Insights e Monitoramento](/schooldatasync/sds-for-insights-data-health-and-monitoring).

> [!IMPORTANT]
> Se você tiver problemas, a [atendimento ao cliente](https://aka.ms/edusupport) você estiver lá para ajudá-lo.

## <a name="supported-grade-level-values"></a>Valores de nível de notas com suporte

Nos arquivos SDS, nível de série/ano definido como valores Enumerados, o que significa que você só pode fornecer um conjunto selecionado de valores dentro do arquivo CSV. Qualquer coisa diferente dos valores especificados resultará em um erro durante o processamento de sincronização.

A seção abaixo define os valores suportados no arquivo de usuários.

### <a name="united-states--worldwide-grade-levels"></a>Estados Unidos/níveis de classificação em todo o mundo
|Valor no arquivo (Coluna de nota) | Rótulo no Insights|
|:---|:---| 
|TI|Infantil|
|PR|Pré escola|
|PK|Pré-jardim de infância|
|TK|Jardim de Infância Transicional|
|KG|Jardim da infância|
|01 ou 1|Primeiro ano|
|02 ou 2|Segundo ano|
|03 ou 3|Terceiro ano|
|04 ou 4|Quarto ano|
|05 ou 5|Quinto ano|
|06 ou 6|Sexto ano|
|07 ou 7|Sétimo ano|
|08 ou 8|Oitavo ano|
|09 ou 9|Nono ano|
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
|01 ou 1|Ano 1|
|02 ou 2|Ano 2|
|03 ou 3|Ano 3|
|04 ou 4|Ano 4|
|05 ou 5|Ano 5|
|06 ou 6|Ano 6|
|07 ou 7|Ano 7|
|08 ou 8|Ano 8|
|09 ou 9|Ano 9|
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

