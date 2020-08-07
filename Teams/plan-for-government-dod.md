---
title: Implantação do governo do Office 365 – implementações do DoD
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Orientação para profissionais de ti para conduzir implantações do Office 365 em entidades que lidam com os dados sujeitos a normas do governo dos EUA.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04b0833f453ffac96e9fe2c9cef1b0f2a0797ca2
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581252"
---
# <a name="plan-for-office-365-government---dod-deployments"></a>Plano para implantações do Office 365 governo-DoD

Esta orientação é para os profissionais de ti que estão impulsionando implantações do Office 365 em entidades governamentais federais dos EUA ou outras entidades que lidam com os dados sujeitos a normas e requisitos governamentais, em que o uso do governo do Office 365 – DoD é adequado para atender a esses requisitos.

> [!NOTE]
> Se a sua organização já atendeu aos requisitos de qualificação do governo do Office 365 e se aplicou e foi aceito no programa, você pode ignorar as etapas 1 e 2 e ir diretamente para a etapa 3.

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a>Etapa 1. Determine se a sua organização precisa do Office 365 governo-DoD e atenda aos requisitos de qualificação. 

O ambiente governo/governo do Office 365 fornece conformidade com os requisitos governamentais dos EUA para serviços de nuvem. Além de desfrutar dos recursos e funcionalidades do Office 365, as organizações se beneficiam dos seguintes recursos exclusivos do Office 365 governo – DoD:

- O conteúdo do cliente da sua organização é logicamente segregado do conteúdo do cliente nos serviços comerciais do Office 365 da Microsoft.
- O conteúdo do cliente da sua organização é armazenado nos Estados Unidos.
- O acesso ao conteúdo do cliente da sua organização está restrito ao pessoal da Microsoft em tela.
- O governo do Office 365 – DoD está em conformidade com certificações e capacitações necessárias para clientes do setor público dos EUA.

Você pode encontrar mais informações sobre o governo do Office 365 – ofertas do governo dos EUA para clientes do governo dos EUA em [planos do governo do office 365](https://products.office.com/government/compare-office-365-government-plans), incluindo [requisitos de qualificação](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

A [Descrição do serviço governo dos EUA do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) descreve as vantagens da plataforma, que são centralizadas em requisitos de conformidade de reunião nos Estados Unidos.


> [!Tip]
> Talvez você queira transferir as tabelas de informações na descrição do serviço para uma pasta de trabalho do Excel e adicionar duas colunas: **pertinentes para minha organização y/n** e **atender às necessidades da minha organização y/n**. Em seguida, você pode revisar essa lista com seus colegas para confirmar que esse serviço atende às necessidades da sua organização.


|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se o Office 365 governo-DoD é apropriado para sua organização.</li><li>Confirme se a sua organização atende aos requisitos de qualificação.</li></ul> |

> [!Note]
> O Office 365 governo-DoD só está disponível nos Estados Unidos. Os clientes do governo dos EUA podem escolher entre vários [planos governamentais do Office 365](https://products.office.com/en/government/compare-office-365-government-plans).

## <a name="step-2-apply-for-office-365-government---dod"></a>Etapa 2. Aplique-se ao Office 365 governo-DoD

Decidisse que esse serviço é ideal para sua organização, inicie o processo de [aplicação para este serviço](https://products.office.com/government/eligibility-validation).


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a>Etapa 3. Compreenda as configurações de segurança padrão do governo do Office 365-DoD.

Recomendamos que você leve tempo para revisar cuidadosamente suas [configurações de administrador e de segurança](enable-features-office-365.md) antes de modificá-las e considerar o impacto sobre a conformidade antes de fazer qualquer alteração nas configurações de segurança padrão.

|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Decida se você precisará modificar qualquer uma das configurações de segurança do governo padrão do Office 365, resolvendo para compreender primeiro o impacto das alterações que você pode fazer.</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a>Etapa 4. Entender quais recursos do teams estão disponíveis no momento no governo do Office 365-DoD

Para acomodar os requisitos de nossos clientes de nuvem governamental, há algumas diferenças entre as equipes do Office 365 governo-DoD e equipes nos planos empresariais. Consulte a tabela a seguir para ver os recursos disponíveis.

[Descrição do serviço do Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>Etapa 5. Plano de governança

Determine suas necessidades de governança e como você pode atendê-las. Vá para [plano de governança no Teams](plan-teams-governance.md) para obter mais informações.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Ponto de decisão |<ul><li>Determine e documente seus requisitos de governança, seguindo as diretrizes de [plano de controle no Teams](plan-teams-governance.md). </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>Etapa 6. Implantar equipes para colaboração

Depois de ter sido integrado ao Office 365 governo – DoD, siga o caminho de implantação recomendado descrito em [como implantar o Microsoft Teams](How-to-roll-out-teams.md). Não deixe de entrar em contato com sua equipe de adoção e gerenciamento de mudanças e especialistas do teams.

Você também pode trabalhar com o [FastTrack](https://www.microsoft.com/fasttrack) ou o parceiro escolhido para onboard do serviço.
