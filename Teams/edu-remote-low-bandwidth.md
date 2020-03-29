---
title: Diretrizes para baixa largura de banda do Microsoft Teams para EDU
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Artigo do Microsoft Teams para EDU para auxiliar com problemas de áudio e vídeo relacionados à baixa largura de banda. Se você for um dos pais, professor ou administrador de TI, terá opções para melhorar a experiência com o Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f34ea2e65906c648081a019d6acf8a3f8a5cd5
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43034061"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a>Ajuda para situações de baixa largura de banda para as Teams para EDU

Há muitos elementos de rede, no que se refere a trabalhar com o Microsoft Teams, que podem afetar o desempenho, e a baixa largura de banda é uma das situações que podem dar a sensação de estar fora do seu controle. Considere o seguinte:

- Uma conexão de internet de baixa velocidade para a escola.
- Uma conexão de internet de baixa velocidade para um ou mais alunos.
- Períodos do dia em que há baixa largura de banda devido ao uso da rede em uma região.
- Períodos de baixa largura de banda devido a paralisações locais não relacionadas à escola ou alunos, mas que ainda assim impactam na performance.
- Problemas não relacionados à largura de banda (por exemplo, problemas com hardware) confundidos como problemas de baixa largura de banda.

Este artigo lhe oferece práticas recomendadas a seguir para diversas atividades do Teams quando você estiver enfrentando um problema de baixa largura de banda.

> [!IMPORTANT]
> Aqui tem informação sobre [Como o Microsoft Teams utiliza memória](teams-memory-usage-perf.md), porque além dos problemas de baixa largura de banda, você pode ter problemas com os recursos do seu dispositivo. Se você estiver procurando por diretrizes de rede do Microsoft Teams, confira [Preparar a rede da sua organização para o Microsoft Teams](prepare-network.md).

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a>Solucionar problemas de baixa largura de banda para Administradores de TI

O importante a ser lembrado, como um Administrador de TI, é que, embora você tenha soluções para problemas de baixa largura de banda amplos que possam ser solucionados rapidamente, isso deve ser analisado cuidadosamente, pois alguns problemas podem ser resolvidos com um foco mais estreito no professor ou até mesmo no nível de aluno/pais.

Resumindo, se o problema de baixa largura de banda ocorrer em um grande grupo de alunos, executar uma ação como um Administrador de TI faz sentido, e também faz sentido se as ações executadas no nível aluno/professor ainda não tiveram sucesso.

> [!NOTE]
> Se você tem a oportunidade de investir, o [Guia de Revisão de Qualidade da Experiência](quality-of-experience-review-guide.md) é uma leitura válida (não é específica de EDU, mas ainda assim terá informações valiosas). Isso permitirá que Administradores de TI experientes se aprofundem na experiência dos professores e alunos.

### <a name="meetings-and-video"></a>Reuniões e vídeo

Um foco principal para problemas de baixa largura de banda são reuniões e vídeos em reuniões. A seguir, listamos algumas das ações que uma Administrador de TI deve considerar ao lidar com problemas relatados por alunos ou professores no que se refere a ter uma melhor experiência de reunião em um ambiente escolar.

#### <a name="meeting-policies"></a>Políticas de reunião

Em relação às reuniões, uma das áreas de maior preocupação para as situações de baixa largura de banda tem a ver com os vídeos. Felizmente, além do Teams ser capaz de dimensionar automaticamente a largura de banda detectada, você como um Administrador de TI tem opções à política que podem ser definidas conforme o organizador e/ou usuário para oferecer a todos a melhor experiência, à luz da largura de banda com a qual precisam trabalhar em um determinado período.

Algumas das coisas que você pode definir por meio da política incluem:

- Desabilitar o vídeo completamente, para que ninguém possa habilitá-lo.
- Taxa de bits de mídia (definida por usuário).

Para saber mais sobre suas opções e para um resumo das especificações de quais políticas você precisaria definir para reuniões e vídeos, confira [Configurações de política de reunião no Teams: Áudio e vídeo](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video) para obter informações detalhadas.

#### <a name="screen-sharing-policies"></a>Políticas de compartilhamento de tela

Em outros casos, professores podem estar compartilhando toda a tela com os alunos, quando o compartilhamento deve ser limitado a um aplicativo relevante à lição que está sendo ensinada. Isso também pode ser definido pela política, se essa opção for mais interessante do que fazer com que os professores façam essa escolha individualmente.

Para ter uma boa ideia do que você pode fazer para limitar o compartilhamento de tela por meio das configurações de política, confira [Configurações de política de reunião no Teams: Compartilhamento de tela](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video).

#### <a name="dial-in-number-for-meetings"></a>Números de discagem para reuniões

Pode ser mais fácil para os alunos tentarem discagem para algumas sessões da sala de aula. Você pode fornecer um número de discagem para reuniões no Teams, para que os alunos com dificuldades possam telefonar como uma alternativa para participar de uma reunião de vídeo.

Para saber mais sobre isso, você pode ler [Definir os números de telefone incluídos em convites no Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="low-bandwidth-scenarios-as-an-educator"></a>Cenários de baixa largura de banda como um professor

Os professores devem ter uma capacidade de resolver problemas de baixa largura de banda e podem ser uma melhor opção às ações de Administradores de TI nas seguintes situações:

- Se o problema for intermitente ou relativamente passageiro.
- Se houver um horário específico do dia em que você pode antecipar a existência de um problema ou se o período de baixa largura de banda tiver alguma previsibilidade.

Nesses casos, você pode executar algumas ações.

Para obter mais informações, confira [Usar o Teams para a trabalhos escolares quando a largura de banda estiver baixa](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>Cenários de baixa largura de banda como pai ou aluno

Há situações também, e você deve discuti-las proativamente com seus professores, onde o problema de largura de banda pode estar no lado do aluno (por exemplo, um grande número de alunos pode assistir as lições de vídeo sem problemas, mas um pequeno número de alunos pode ter dificuldades).

Não é razoável esperar que muitos pais possam solucionar esses problemas, e problemas de baixa largura de banda podem estar fora do controle de um aluno ou pai (sua casa pode não ter acesso à alta largura de banda, pode ter uma grande quantidade de pessoas em sua vizinhança consumindo banda e afetando o que elas podem fazer, pode haver instabilidade na Internet e assim por diante).

Reunimos as diretrizes em nosso artigo [Usar o Teams para dever de casa quando a largura de banda estiver baixa](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) para pais e alunos, e, além disso, você pode revisar e testar essas recomendações se estiver tendo problemas.
