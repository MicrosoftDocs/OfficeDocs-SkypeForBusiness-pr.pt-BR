---
title: Início rápido de governança no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
ms.localizationpriority: medium
search.appverid: MET150
description: Início rápido que abrange as principais decisões que você precisará tomar para a fase 2 do seu plano de Microsoft Teams de adoção.
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
ms.openlocfilehash: eaeec25c90e800fcc688dad924ecac8de687841a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733710"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>Início rápido de governança no Microsoft Teams

As atividades a seguir ocorrerão simultaneamente e podem envolver toda ou parte da sua equipe-chave. Como prática prática prática, adie as conversas de segurança e governança em grande escala para depois de concluir sua experimentação inicial com Teams. É importante entender como as decisões de governança podem afetar a experiência do usuário final e simplificará as decisões que você precisará tomar nessa data posterior. Para essa fase, há algumas decisões que precisam ser tomadas. Para torná-los com êxito, primeiro você precisará responder às seguintes perguntas:

- Qual stakeholder da sua avaliação anterior é um bom candidato para participar dessa integração de negócios limitada?
- Esse indivíduo (ou grupo de indivíduos) sugere casos de uso que seriam bons candidatos para essa fase?  
- Eles têm interesse suficiente dos funcionários em sua organização para serem adotantes antecipados e dar feedback significativo e regular? 

Para saber mais, leia [Plan for governance in Teams](plan-teams-governance.md) and Plan for lifecycle management in [Teams](plan-teams-lifecycle.md).

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![Um ícone que representa um ponto de decisão.](media/teams-adoption-decision-icon.png)Decisões

Tomar as seguintes decisões (neste ponto, essas decisões se aplicam somente à Fase 2):

### <a name="decision-1-who-can-create-teams"></a>Decisão 1: Who pode criar equipes 

Para os fins desta fase, você pode restringir quem é capaz de criar equipes para a população de adotadores antecipados, além da sua equipe principal do projeto. Isso permitirá que seus primeiros adotantes criem equipes adicionais, se necessário. O monitoramento desse comportamento lhe dará informações importantes para sua implantação ampla.

### <a name="decision-2-teams-naming-conventions"></a>Decisão 2: Teams de nomenis 

Você provavelmente vai querer implementar algumas convenções de nomenis para sua ampla implantação de Teams e verificar se há nomes duplicados. Na Fase 2, sugerimos que você implemente uma convenção de nomenisão manual apenas para seus projetos iniciais. A prática mais prática para isso é conduzir uma integração interativa com a equipe de projeto do adotante inicial e permitir que eles selecionem seu próprio nome. Isso dará uma visão de como os funcionários pensam sobre seu trabalho e serão essenciais na criação de uma convenção de nomenis de maior escala posteriormente. (Informações adicionais sobre os elementos de uma integração interativa serão exibidas posteriormente neste guia.)

### <a name="decision-3-guest-access"></a>Decisão 3: Acesso de convidados

Dependendo do escopo e do tipo do seu projeto e da natureza do seu setor, habilitar a colaboração segura com parceiros ou fornecedores pode ser um recurso essencial que você deseja testar. Você pode limitar quem pode adicionar convidados às equipes usando os controles de locatário apropriados e limitar quais equipes estão abertas aos convidados usando rótulos de sensibilidade. Você também pode garantir que os convidados aderam aos requisitos de segurança organizacional, como o uso da Autenticação Multifaionária (MFA).

### <a name="decision-4-approved-apps"></a>Decisão 4: Aplicativos aprovados

O melhor caso de uso de Teams inclui a integração de outros aplicativos à experiência. No mínimo, sua equipe técnica deve habilitar os aplicativos de primeira parte e recursos em sua Teams experiência. Dependendo do caso de uso e de outros aplicativos usados em sua organização, você pode optar por incluir aplicativos adicionais como parte do experimento controlado. Certifique-se de vetar todos os aplicativos de terceiros para garantir que eles aderam aos requisitos de segurança e conformidade da sua organização.

### <a name="decision-5-are-meetings-included-in-your-test"></a>Decisão 5: As reuniões estão incluídas no teste? 

A Teams de reunião é de alta qualidade, dá suporte a conversas em vídeo e reúne seus funcionários para serem mais eficientes. Consulte sua equipe técnica para garantir que seu ambiente esteja pronto para incluir reuniões VoIP simples. A habilitação de serviços de audioconferência ou voz normalmente seria excluída dessa fase de sua experimentação; no entanto, isso depende da equipe principal do projeto, da preparação técnica e do estado de outros serviços de voz/reunião em sua organização. A preparação técnica deve incluir coisas como equipamentos de sala de reunião, dispositivos e acessórios do usuário final e a rede. Recomendamos incluir chats em vídeo e reuniões VoIP em sua experimentação para obter mais valor com sua implementação Teams. 

### <a name="decision-6-content-management-and-structure"></a>Decisão 6: Gerenciamento e estrutura de conteúdo
Teams funciona melhor quando os usuários trabalham de ponta a ponta dentro da plataforma - em vez de exigir que eles mudem continuamente de volta para sistemas e serviços herdados - e oferece novas maneiras de trabalhar que diferem de como os usuários estão acostumados. Como parte do seu experimento, trabalhe com seus participantes para considerar as estruturas e canais de equipe que adotam as formas multi-modais de colaboração dentro do Teams e evitem simplesmente replicar estruturas de armazenamento e pastas existentes. Além disso, considere quaisquer requisitos de conformidade para conteúdo armazenado fora de sistemas suportados existentes, como gerenciamento de registros ou sistemas de backup.

### <a name="decision-7--data-security"></a>Decisão 7: Segurança de dados

Em preparação para sua ampla implantação, você pode optar por usar rótulos de segurança para classificar os tipos de equipes em seu ambiente. Para os fins deste experimento, recomendamos que você consulte [Plan for Governance in Teams](plan-teams-governance.md) e verifique se uma política de retenção básica foi definida em Teams dados em seu Microsoft 365. Talvez seja necessário coordenar esse trabalho com sua equipe técnica, pois Microsoft 365 direitos de administrador são necessários para concluir esse trabalho.

### <a name="decision-8-length-of-your-experiment"></a>Decisão 8: Duração do seu experimento

Uma implementação Teams bem-sucedida continua em um ritmo ímpeto para garantir o momento, o foco e os aprendizados apropriados. Recomendamos que essa fase do seu projeto seja de 60 dias para garantir que seus primeiros adotantes concluam ciclos de negócios suficientes. Estender a experimentação por muito tempo aumenta o risco de um programa de alteração com falha; no entanto, esse tempo variará para cada organização.  

![Um ícone que representa a próxima etapa.](media/teams-adoption-next-icon.png) Em seguida: [Definir cenários de uso](teams-adoption-define-usage-scenarios.md)
