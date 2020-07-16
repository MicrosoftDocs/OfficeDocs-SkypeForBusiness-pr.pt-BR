---
title: Microsoft Teams Class Insights para Administradores de TI
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Um guia ITAdmin para o Class Insights do Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbf535c73bd1b23b22f368707bcbabe44c0cdf2d
ms.sourcegitcommit: 2cc36c954200f50de33b909856b33fe0a9a6b7a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126184"
---
# <a name="class-insights-for-it-admins"></a>Class Insights para Administradores de TI

Com o Class Insights no Microsoft Teams, os educadores podem acessar dados analíticos sobre o envolvimento e desempenho dos alunos. O Class Insights coleta as atividades do aluno no Teams, como notas, entrega de tarefas, atividade de comunicação e colaboração de arquivos, criando um painel de análise que exibe elementos visuais de dados práticos.

O Class Insights está ativo nos SKUs A1, A3 e A5 do Office 365 Education.

> [!NOTE]
> Educadores, aprendam a usar o Class Insights [aqui](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc).

## <a name="permissions"></a>Permissões

Os educadores podem adicionar o Class Insights a um canal público em uma equipe de classe, navegando até Aplicativos na barra de aplicativos do Teams e pesquisando Insights.

- Os educadores são definidos por licenças do corpo docente. Os educadores devem ter uma licença do corpo docente e ser proprietário de uma equipe de classe para adicionar e ver a guia Insights.
- Os alunos são identificados por sua licença e **não têm acesso à guia Insights** (mesmo que sejam proprietários da equipe).
- A guia reflete as atividades de todos na equipe de classe que não são proprietários (incluindo educadores que não são proprietários da equipe).

## <a name="compliance"></a>Conformidade

O Class Insights possui compromissos de conformidade líderes do setor e é classificado como um serviço de Nível C na Estrutura de Conformidade do Office 365.

> [!NOTE]
> Visite a [Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center) para saber mais sobre como a Microsoft protege seus dados.

## <a name="privacy"></a>Privacidade

As informações coletadas e exibidas através do Class Insights atendem a mais de 90 padrões regulamentares e do setor, incluindo o GDPR e a Lei dos Direitos Educacionais e Privacidade da Família (FERPA) para a segurança dos alunos e crianças e outras regulamentações semelhantes, voltadas à privacidade. É importante que os ITAdmins saibam que as informações coletadas dos alunos devem ser usadas apenas em um contexto de classe, para permitir que os educadores determinem o comportamento da classe. As informações são coletadas para atividades de aprendizado significativas, como participação em reuniões de classe, postagem de mensagens, resposta às postagens dos colegas, execução de tarefas, edição de arquivos e muito mais. Não mostramos informações sobre o chat privado ou logon do Teams, por exemplo.

Nosso objetivo é ajudar os educadores a entender o engajamento e focar no aprendizado dos alunos. Embora essas atividades de classe possam ser concentradas em ações no nível do aluno, não há nenhum valor positivo ou negativo atribuído a essas ações pelo Microsoft Teams, e não há identificação crítica de alunos individuais com base em critérios. As informações no Class Insights mostram a um educador que, por exemplo, um aluno não está ativo na ferramenta durante um determinado período de tempo ou que ele concluiu todas as suas tarefas na semana passada, pontualmente. É responsabilidade do educador interagir com o aluno e sua família ou responsáveis ​​para determinar a razão subjacente a qualquer atividade ou inatividade detectada.

## <a name="data-collection"></a>Coleta de dados

Coletamos dados do Class Insights quando a Análise Educacional está ativada para o locatário. Os dados são coletados das atividades do Teams para apresentar insights práticos ​​de ensino e aprendizagem.

Por padrão, a Análise Educacional está **Habilitada**.

Atualmente, esses dados são extraídos das seguintes áreas de atividade de alunos e educadores nas equipes de classe:

|Componente do Teams  |Dados coletados  |
|-----------------|------------------------|------------------------|
|Atribuições |Abrir, entregar e dar nota a tarefas. |
|Envolvimento no canal |Visitar um canal, criar uma postagem, responder e curtir uma postagem (sem incluir o conteúdo do chat). |
|Arquivos |Upload, download, acesso, modificação, comentário e compartilhamento de um arquivo (não incluindo o conteúdo do arquivo). |
|Reuniões |Participação (sem incluir o conteúdo da reunião). |

## <a name="data-location"></a>Local dos dados

Os dados do Class Insights de locatários provenientes da Europa são armazenados em servidores na Europa. Os dados de locatários provenientes dos EUA são armazenados em servidores nos Estados Unidos. Se você usa o Class Insights e seu locatário do Office 365 estiver em uma região fora da Europa ou dos Estados Unidos, seus dados serão armazenados na região geográfica apropriada.

## <a name="performance-and-reliability"></a>Desempenho e confiabilidade

O Class Insights foi projetado para lidar com um alto volume de dados coletados da atividade do Teams com desempenho e confiabilidade ideais.

O processo de coleta de dados ocorre em servidores separados, independentemente da instalação da guia Insights no Teams. A guia Class Insights não afeta o desempenho do aplicativo ou a largura de banda da rede de educadores e alunos que usam as outras funcionalidades do Teams.

> [!TIP]
> Leia [aqui](edu-remote-low-bandwidth.md) sobre o uso do Teams para Educação quando a largura de banda for baixa.

## <a name="how-to-delete-your-data"></a>Como excluir seus dados

Os serviços do Teams para Educação armazenam as ações de alunos e educadores realizadas no contexto de uma equipe de classe. Esses dados são considerados um conjunto de dados combinados e, portanto, não são excluídos automaticamente do serviço depois que as contas de usuário de aluno ou educador são excluídas da sua organização.

> [!NOTE]
> A exclusão de dados tem um impacto negativo na capacidade do Insights de analisar o envolvimento da equipe de classe ao longo do tempo.

- Abra um tíquete de suporte [aqui](https://edusupport.microsoft.com/support). O tíquete de suporte deve declarar claramente a solicitação de uma operação GDPR Delete DSR e conter a ID de objeto de usuário a ser excluída. Não é possível limitar o conjunto de dados ou a janela de tempo da exclusão.
- Uma vez arquivado, o tíquete de suporte aguardará na fila por uma semana para atender à política de retenção mínima de conformidade. Você tem a oportunidade de cancelar a operação durante esse período.
- Após uma semana, a equipe da Análise Educacional toma medidas para garantir que todos os dados relacionados à ID do usuário sejam excluídos do serviço. O suporte da Microsoft monitora o tíquete ICM e o notificará assim que o processo de exclusão for concluído, em, no máximo, 28 dias.

## <a name="turn-insights-off-and-on-using-school-data-sync-sds"></a>Habilitar e desabilitar o Insights usando o School Data Sync (SDS)

O School Data Sync (SDS) ajuda a automatizar o processo de importação e sincronização de dados do Sistema de Informações de Aluno (SIS) com o Office 365.

O uso do Class Insights não exige o uso de SDS. No entanto, você pode optar por desativar a Análise Educacional a qualquer momento, desativando a alternância no Centro de Administração do SDS em **Configurações** > **Gerenciar a Análise Educacional**.

:::image type="content" source="media/class-insights-on-off.png" alt-text="A opção ligar/desligar para habilitar ou desabilitar o Class Insights.":::

Por padrão, a Análise Educacional e o Class Insights estão habilitados. Quando você desabilita a Análise, excluímos todos os dados coletados da guia Class Insights. Habilite a Análise novamente e começaremos a coletar dados a partir do momento em que ela for habilitada.

Saiba mais: [Class Insights para educadores](https://support.microsoft.com/office/actionable-analytics-with-class-insights-in-teams-163add4f-997d-4a01-91de-2846fe4e99bc)
