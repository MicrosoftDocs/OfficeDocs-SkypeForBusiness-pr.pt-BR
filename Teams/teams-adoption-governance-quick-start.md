---
title: Início rápido de governança no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
localization_priority: Normal
search.appverid: MET150
description: Início rápido que aborda as principais decisões que você precisará fazer para a fase 2 do seu plano de adoção do Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd54902e00e984de740b7bbf6d0fd96e37e88aa9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424551"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>Início rápido de governança no Microsoft Teams

As atividades a seguir ocorrerão simultaneamente, e podem envolver toda a sua equipe ou parte dela. Como prática recomendada, adie o controle de grandes dimensões e as conversas de segurança para depois de concluir a experimentação inicial com o Teams. É importante compreender como as decisões de governança podem afetar a experiência do usuário final e simplificarão as decisões que você precisará fazer na data mais tarde. Para esta fase, há algumas decisões que precisam ser feitas. Para fazer com que eles sejam bem-sucedidos, você precisará primeiro responder às seguintes perguntas:

- Quais dos interessados de sua avaliação anterior é um bom candidato para participarem de um Conselho de negócios limitado?
- Este indivíduo (ou grupo de indivíduos) sugeriu casos de uso sugeridos que seriam bons candidatos para esta fase?  
- Elas têm interesse suficiente dos funcionários de sua organização para serem pioneiros a adotar e lhe dar comentários significativos e significativos? 

Para saber mais, leia [plano de governança no Teams](plan-teams-governance.md) e [planeje o gerenciamento do ciclo de vida do Microsoft Teams](plan-teams-lifecycle.md).

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![Um ícone representando um ponto de decisão](media/teams-adoption-decision-icon.png)Relacionadas

Faça as seguintes decisões (neste ponto, estas decisões se aplicam apenas à fase 2):

### <a name="decision-1-who-can-create-teams"></a>Decisão 1: quem pode criar equipes 

Para a finalidade desta fase, você pode restringir quem é capaz de criar equipes para a população de adoção inicial, além da sua equipe de projeto principal. Isso permitirá que seus primeiros adeptos criem mais equipes, se necessário. A monitoração desse comportamento oferece informações essenciais para a sua ampla implantação.

### <a name="decision-2-teams-naming-conventions"></a>Decisão 2: convenções de nomenclatura do teams 

Você provavelmente desejará implementar algumas convenções de nomenclatura para a sua implantação ampla do Teams e verificar se há nomes duplicados. Na fase 2 sugerimos que você implemente uma Convenção de nomenclatura manual somente para os projetos iniciais. A prática recomendada para isso é conduzir um integração interativa com a equipe de projeto pioneira e permitir que elas selecionem o nome dela. Isso lhe dará noções básicas sobre como os funcionários pensam em seu trabalho e serão essenciais para criar uma Convenção de nomenclatura de escala maior posteriormente. (Informações adicionais sobre os elementos de um integração interativo serão exibidas posteriormente neste guia.)

### <a name="decision-3-guest-access"></a>Decisão 3: acesso de convidado

Dependendo do escopo e do tipo de seu projeto e da natureza do seu setor, permitir a colaboração segura com parceiros ou fornecedores pode ser um recurso essencial que você deseja testar. Você pode limitar quem pode adicionar convidados às equipes usando os controles de locatário apropriados e limitar quais equipes estão abertas a convidados usando rótulos de sensibilidade. Além disso, você pode garantir que os convidados sigam os requisitos de segurança organizacional, como o uso da MFA (autenticação multifator).

### <a name="decision-4-approved-apps"></a>Decisão 4: aplicativos aprovados

O melhor uso de casos do teams inclui a integração de outros aplicativos na experiência. Pelo menos sua equipe técnica deve habilitar o primeiro e os aplicativos em destaque na experiência de suas equipes. Dependendo de seu caso de uso e de outros aplicativos usados em sua organização, você pode optar por incluir aplicativos adicionais como parte do seu experimento controlado. Não deixe de vet qualquer aplicativo de terceiros para garantir que eles estejam de acordo com os requisitos de segurança e conformidade da sua organização.

### <a name="decision-5-are-meetings-included-in-your-test"></a>Decisão 5: as reuniões estão incluídas em seu teste? 

A experiência de reunião do teams é de alta qualidade, compatível com vídeo em chat e traz seus funcionários para serem mais eficientes. Consulte sua equipe técnica para garantir que seu ambiente esteja pronto para incluir reuniões simples de VoIP. A habilitação da videoconferência ou dos serviços de voz normalmente seria excluída desta fase de experimentação; no entanto, isso depende da sua equipe de projeto principal, da preparação técnica e do estado de outros serviços de voz/reunião em sua organização. A preparação técnica deve incluir itens como equipamento da sala de reuniões, dispositivos e acessórios do usuário final e a rede. Recomendamos incluir chats com vídeo e reuniões VoIP em seu experimento para obter mais valor da implementação de suas equipes. 

### <a name="decision-6-content-management-and-structure"></a>Decisão 6: gerenciamento de conteúdo e estrutura
O Microsoft Teams funciona melhor quando os usuários trabalham de ponta a ponta dentro da plataforma, em vez de exigir que eles voltem continuamente para sistemas e serviços herdados e oferece novas maneiras de trabalhar diferentes de como os usuários estão acostumados. Como parte do seu experimento, trabalhe com seus participantes para considerar estruturas e canais de equipe que englobam as maneiras multirestritas de colaboração no Microsoft Teams e evite simplesmente replicar estruturas de pasta e armazenamento existentes. Além disso, considere todos os requisitos de conformidade para conteúdo armazenado fora dos sistemas compatíveis existentes, como gerenciamento de registros ou sistemas de backup.

### <a name="decision-7--data-security"></a>Decisão 7: segurança de dados

Em preparação para a sua ampla implantação, você pode optar por usar rótulos de segurança para classificar os tipos de equipe em seu ambiente. Para o propósito deste experimento, recomendamos que você faça referência ao [plano de governança no Teams](plan-teams-governance.md) e assegure-se de que uma política de retenção básica tenha sido definida nos dados do teams em seu 365 da Microsoft. Talvez seja necessário coordenar esse trabalho com sua equipe técnica porque os direitos de administrador do Microsoft 365 são necessários para concluir esse trabalho.

### <a name="decision-8-length-of-your-experiment"></a>Decisão 8: duração do seu experimento

Uma implementação de equipe bem-sucedida continua a um ritmo saudável para garantir a impulso, o foco e os aprendizados adequados. Recomendamos que esta fase do seu projeto tenha 60 dias de duração para garantir que seus primeiros pioneiros completem ciclos de negócios suficientes. Estendendo a experimentação por muito tempo aumenta o risco de um programa de alteração com falha; no entanto, esse tempo vai variar para cada organização.  

![Um ícone que representa a próxima etapa ](media/teams-adoption-next-icon.png) seguinte: [definir cenários de uso](teams-adoption-define-usage-scenarios.md)
