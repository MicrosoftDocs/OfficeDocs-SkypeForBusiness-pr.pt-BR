---
title: Guia para o Administrador de TI sobre o Insights no Teams para Educação
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Um guia para o Administrador de TI sobre o Insights no Microsoft Teams para Educação.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b63ea1a1a09a55d9a51fb2a110c024960f23f6f4
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803519"
---
# <a name="it-admin-guide-to-insights-in-teams-for-education"></a>Guia para o Administrador de TI sobre o Insights no Teams para Educação

Com o Insights no Microsoft Teams para Educação, educadores e líderes podem acessar dados analíticos sobre envolvimento digital, carga de trabalho de atribuição, notas, comunicação e muito mais. O Insights é orientado por princípios éticos que colocam educadores e alunos em primeiro lugar, atende aos padrões de privacidade e garante conformidade contínua para sua instituição.

O Insights está ativo nos SKUs A1, A3 e A5 do Office 365 Education.

> [!NOTE]
> Educadores, aprendam como usar o Insights aqui [Guia do educador para o Insights no Microsoft Teams](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181).

## <a name="use-insights"></a>Usar o Insights

### <a name="user-types"></a>Tipos de usuário:
- Os **alunos** são identificados por sua licença e  _não têm_ acesso à guia Insights (mesmo que sejam proprietários da equipe). 
- **Educadores** são identificados pelas licenças do corpo docente. Os educadores devem ter uma licença do corpo docente e ser proprietário de uma equipe de classe para adicionar e ver os dados apresentados na guia Insights. 
- Os **líderes** também são identificados pelas licenças do corpo docente, mas além disso, eles precisam de permissões explícitas do administrador global de TI para visualizar os relatórios no aplicativo Insights.
- As contas de convidado _não têm_ acesso ao Insights.

### <a name="entry-points"></a>Pontos de entrada
Educadores e líderes têm diferentes pontos de entrada onde podem descobrir e usar o Insights.

**Educadores** podem usar estes dois pontos de entrada:
- [Guias](https://support.microsoft.com/article/27b56255-90c0-47aa-bac3-1c9f50157181) - percepções para cada classe que eles possuem estão disponíveis em uma guia adicionada no menu de navegação superior. O Insights revelará dados de atividade de todos os canais de uma equipe de turma, mas só pode ser adicionado como uma guia para canais públicos. A guia reflete a atividade de todos na equipe da turma que não são proprietários (incluindo educadores que não são donos da equipe).
- [Aplicativo pessoal](https://support.microsoft.com/article/747fd8d9-00b0-43e6-bacc-a1bf030b1867) - uma visão geral de todas as suas classes ativas está disponível na barra esquerda do aplicativo Teams.

**Líderes** podem usar o Insights como um [aplicativo pessoal](https://support.microsoft.com/article/8738d1b1-4e1c-49bd-9e8d-b5292474c347).

### <a name="manage-setup-policy"></a>Gerenciar política de configuração
Como administrador, você pode usar a [política de configuração do aplicativo](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies) para instalar o Insights por padrão para seus educadores e líderes quando eles iniciam o Teams.
Com essa política, pode-se personalizar o Teams para destacar as percepções e fixá-las na barra de aplicativos.

> [!TIP]
> Leia [Políticas do Teams e Pacotes de Políticas para a Educação](https://docs.microsoft.com/microsoftteams/policy-packages-edu) sobre as políticas de equipes e pacotes de políticas para educação.



## <a name="compliance"></a>Conformidade

O Insights tem compromissos de conformidade líderes do setor e é classificado como um serviço de Nível C na Estrutura de Conformidade do Office 365.

> [!NOTE]
> Visite a [Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center) para saber mais sobre como a Microsoft protege seus dados.

## <a name="privacy"></a>Privacidade

As informações coletadas e mostradas por meio do Insights atendem a mais de 90 padrões regulatórios e industriais, incluindo o GDPR e a Lei de Direitos e Privacidade da Educação da Família (FERPA) para a segurança de alunos e crianças, além de outras regulamentações semelhantes voltadas para a privacidade. É importante que os administradores de TI saibam que as informações coletadas por aluno devem ser usadas apenas no contexto da turma, para permitir que educadores e líderes determinem o comportamento dos alunos. As informações são coletadas para atividades de aprendizado significativas, como participação em reuniões de classe, postagem de mensagens, resposta às postagens dos colegas, execução de tarefas, edição de arquivos e muito mais. Não mostramos informações sobre o chat privado ou logon do Teams, por exemplo.

Nosso objetivo é ajudar os educadores a entender o engajamento e focar no aprendizado dos alunos. Embora essas atividades de classe possam ser concentradas em ações ao nível do aluno, não há nenhum valor positivo ou negativo atribuído a essas ações pelo Microsoft Teams, e não há identificação crítica de alunos individuais com base em critérios. As informações no Insights informam ao educador que, por exemplo, um aluno não esteve ativo na ferramenta durante um determinado período de tempo, ou concluiu todas as suas tarefas na semana passada no prazo determinado. É responsabilidade do educador interagir com o aluno e sua família ou responsáveis ​​para determinar a razão subjacente a qualquer atividade ou inatividade detectada.

## <a name="data-collection"></a>Coleta de dados

- Coletamos os dados para o Insights quando o Education Analytics é ativado para o locatário. Os dados são coletados das atividades do Teams para apresentar insights práticos ​​de ensino e aprendizagem.
- Os dados de convidados _não_ são coletados para o Insights.
- Por padrão, a Análise Educacional está **Habilitada** .

Atualmente, esses dados são extraídos das seguintes áreas de atividade de alunos e educadores nas equipes de classe:

|Componente do Teams  |Dados coletados  |
|-----------------|------------------------|------------------------|
|Atribuições |Abrir, entregar e dar nota a tarefas. |
|Envolvimento no canal |Visitar um canal, criar uma postagem, responder e curtir uma postagem (sem incluir o conteúdo do chat). |
|Arquivos |Upload, download, acesso, modificação, comentário e compartilhamento de um arquivo (não incluindo o conteúdo do arquivo). |
|Reuniões |Participação (sem incluir o conteúdo da reunião). |

## <a name="data-location"></a>Local dos dados

Os dados do Insights para locatários europeus são armazenados em servidores na Europa. Os dados de locatários provenientes dos EUA são armazenados em servidores nos Estados Unidos. Se você utilizar o Insights e seu locatário do Office 365 estiver em uma região fora da Europa ou dos Estados Unidos, seus dados serão armazenados na região geográfica apropriada.

## <a name="performance-and-reliability"></a>Desempenho e confiança

O Insights foi projetado para lidar com um grande volume de dados coletados das atividades das equipes e com um ótimo desempenho e confiabilidade.

O processo de coleta de dados ocorre em servidores separados, independentemente da instalação da guia Insights no Teams. A guia Insights ou o aplicativo pessoal não afeta o desempenho do aplicativo ou a largura de banda da rede para os educadores e alunos que utilizam o restante da funcionalidade do Teams.

> [!TIP]
> Leia a [Ajuda para situações de baixa largura de banda para o Teams for EDU](edu-remote-low-bandwidth.md) sobre como usar o Teams for Education quando a largura de banda é baixa.

## <a name="how-to-delete-your-data"></a>Como excluir seus dados

Os serviços do Teams para Educação armazenam as ações de alunos e educadores realizadas no contexto de uma equipe de classe. Esses dados são considerados um conjunto de dados combinados e, portanto, não são excluídos automaticamente do serviço depois que as contas de usuário de aluno ou educador são excluídas da sua organização.

> [!NOTE]
> A exclusão de dados tem um impacto negativo na capacidade do Insights de analisar o envolvimento da equipe de classe ao longo do tempo.

- Abra um tíquete de suporte em [https://edusupport.microsoft.com/support](https://edusupport.microsoft.com/support). O tíquete de suporte deve declarar claramente a solicitação de uma operação GDPR Delete DSR e conter a ID de objeto de usuário a ser excluída. Não é possível limitar o conjunto de dados ou a janela de tempo da exclusão.
- Uma vez arquivado, o tíquete de suporte aguardará na fila por uma semana para atender à política de retenção mínima de conformidade. Você tem a oportunidade de cancelar a operação durante esse período.
- Após uma semana, a equipe da Análise Educacional toma medidas para garantir que todos os dados relacionados à ID do usuário sejam excluídos do serviço. O suporte da Microsoft monitora o tíquete ICM e o notificará assim que o processo de exclusão for concluído, em, no máximo, 28 dias.

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a>Habilitar e desabilitar o Insights usando o School Data Sync (SDS)

O School Data Sync (SDS) ajuda a automatizar o processo de importação e sincronização de dados do Sistema de Informações de Aluno (SIS) com o Office 365.

A utilização de Insights não requer o uso de SDS. No entanto, você pode optar por desativar a Análise Educacional a qualquer momento, desativando a alternância no Centro de Administração do SDS em **Configurações** > **Gerenciar a Análise Educacional** .

:::image type="content" source="media/class-insights-on-off.png" alt-text="A opção liga/desliga para ativar ou desativar o Insights.":::

Por padrão, Education Analytics e, portanto, o Insights, está ativado. Quando você desativa o Analytics, excluímos todos os dados coletados para a guia Insights. Ligue o Analytics novamente e começaremos a coletar novamente os dados a partir do momento em que ele é reativado.

## <a name="additional-resources"></a>Recursos adicionais
- [Guia do educador para o Insights](https://support.microsoft.com/office/27b56255-90c0-47aa-bac3-1c9f50157181)
