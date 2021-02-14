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
description: Início rápido que abrange as principais decisões que você precisará tomar para a fase 2 do seu plano de adoção do Microsoft Teams.
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

As seguintes atividades ocorrerão simultaneamente, e elas podem envolver toda ou parte da sua equipe principal. Como prática prática, adia as conversas de segurança e governança em grande escala para depois de concluir a experiência inicial com o Teams. É importante entender como as decisões de gestão podem afetar a experiência do usuário final e simplificar as decisões que você precisará tomar nessa data posterior. Para essa fase, há algumas decisões que precisam ser tomadas. Para torná-las com êxito, primeiro você precisará responder às seguintes perguntas:

- Qual dos participantes da sua avaliação anterior é um bom candidato para participar dessa integração limitada de negócios?
- Esse indivíduo (ou grupo de indivíduos) tem casos de uso sugeridos que seriam bons candidatos para essa fase?  
- Eles têm interesse suficiente dos funcionários em sua organização para serem usuários antecipados e fazer comentários significativos e regulares? 

Para saber mais, leia [o Plano de governança](plan-teams-governance.md) no Teams e [planeje o gerenciamento do ciclo de vida no Teams.](plan-teams-lifecycle.md)

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![Um ícone representando um ponto de decisão](media/teams-adoption-decision-icon.png)Decisões

Tomar as seguintes decisões (neste momento, essas decisões se aplicam apenas à Fase 2):

### <a name="decision-1-who-can-create-teams"></a>Decisão 1: quem pode criar equipes 

Para os fins desta fase, você pode restringir quem é capaz de criar equipes para a população de usuários antecipados, além de sua equipe principal do projeto. Isso permitirá que os primeiros adotores criem equipes adicionais, se necessário. Monitorar esse comportamento lhe dará informações importantes para sua ampla implantação.

### <a name="decision-2-teams-naming-conventions"></a>Decisão 2: convenções de nomen das equipes 

Você provavelmente vai querer implementar algumas convenções de nomen como uma ampla implantação do Teams e verificar se há nomes duplicados. Na Fase 2, sugerimos que você implemente uma convenção de nomenplicação manual apenas para seus projetos iniciais. A prática mais prática para isso é conduzir uma integração interativa com a equipe de projeto do usuário antecipado e permitir que ele selecione seu próprio nome. Isso lhe dará informações sobre como os funcionários pensarão sobre seu trabalho e serão essenciais na criação de uma convenção de nomenuidade em escala maior posteriormente. (Informações adicionais sobre os elementos de uma integração interativa serão exibidas mais adiante neste guia.)

### <a name="decision-3-guest-access"></a>Decisão 3: Acesso de convidado

Dependendo do escopo e do tipo do seu projeto e da natureza do seu setor, permitir a colaboração segura com parceiros ou fornecedores pode ser um recurso essencial que você deseja testar. Você pode limitar quem pode adicionar convidados às equipes usando os controles de locatário apropriados e limitar quais equipes estão abertas para convidados usando rótulos de sensibilidade. Além disso, você pode garantir que os convidados cumpram os requisitos de segurança organizacional, como o uso da MFA (Autenticação Multifatória).

### <a name="decision-4-approved-apps"></a>Decisão 4: aplicativos aprovados

O melhor uso do Teams inclui a integração de outros aplicativos à experiência. No mínimo, sua equipe técnica deve habilitar os primeiros aplicativos e os aplicativos em destaque na sua experiência do Teams. Dependendo do caso de uso e de outros aplicativos usados em sua organização, você pode optar por incluir aplicativos adicionais como parte de sua experiência controlada. Verifique se há aplicativos de terceiros para garantir que eles cumpram os requisitos de segurança e conformidade da sua organização.

### <a name="decision-5-are-meetings-included-in-your-test"></a>Decisão 5: as reuniões estão incluídas no teste? 

A experiência de reunião do Teams é de alta qualidade, dá suporte a chats com vídeo e reúne seus funcionários para serem mais eficazes. Consulte sua equipe técnica para garantir que seu ambiente esteja pronto para incluir reuniões simples do VoIP. A habilitação de serviços de audioconferência ou voz normalmente seria excluída desta fase da sua experiência; no entanto, isso depende da sua equipe de projeto principal, da sua preparação técnica e do estado de outros serviços de voz/reunião em sua organização. A preparação técnica deve incluir coisas como equipamentos de sala de reunião, dispositivos e acessórios do usuário final e a rede. Recomendamos incluir chats com vídeo e reuniões VoIP em sua experiência para obter mais valor com a implementação do Teams. 

### <a name="decision-6-content-management-and-structure"></a>Decisão 6: estrutura e gerenciamento de conteúdo
O Teams funciona melhor quando os usuários trabalham de ponta a ponta dentro da plataforma , em vez de exigir que eles mudem continuamente para sistemas e serviços herdados e oferecem novas maneiras de trabalhar diferentes de como os usuários estão acostumados. Como parte de sua experiência, trabalhe com seus participantes para considerar as estruturas de equipe e os canais que adotam as formas multi-modais de colaboração no Teams e evitem simplesmente replicar estruturas de armazenamento e pastas existentes. Além disso, considere quaisquer requisitos de conformidade para conteúdo armazenado fora de sistemas suportados existentes, como gerenciamento de registros ou sistemas de backup.

### <a name="decision-7--data-security"></a>Decisão 7: Segurança de dados

Em preparação para sua ampla implantação, você pode optar por usar rótulos de segurança para classificar os tipos de equipes em seu ambiente. Para os fins deste experimento, recomendamos que você se refira ao Plano de [Governança](plan-teams-governance.md) no Teams e garanta que uma política de retenção básica tenha sido definida nos dados do Teams em seu Microsoft 365. Talvez seja necessário coordenar esse trabalho com sua equipe técnica, pois os direitos de administrador do Microsoft 365 são necessários para concluir esse trabalho.

### <a name="decision-8-length-of-your-experiment"></a>Decisão 8: duração da experiência

Uma implementação bem-sucedida do Teams é realizada em um ritmo saudável para garantir o momento, o foco e os aprendizados apropriados. Recomendamos que essa fase do seu projeto seja de 60 dias para garantir que os primeiros usuários concluam ciclos de negócios suficientes. Estender a experiência por muito tempo aumenta o risco de um programa de alteração com falha; no entanto, esse tempo variará para cada organização.  

![Um ícone que representa a próxima ](media/teams-adoption-next-icon.png) etapa: [Definir cenários de uso](teams-adoption-define-usage-scenarios.md)
