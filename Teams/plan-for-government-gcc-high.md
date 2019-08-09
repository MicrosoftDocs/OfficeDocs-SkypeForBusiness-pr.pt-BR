---
title: Plano para o Microsoft 365 Government ‒ elevadas implantações de GCC ‒ Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/03/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Orientação para profissionais de ti para conduzir implantações do Office 365 em entidades que lidam com os dados sujeitos a normas do governo dos EUA.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e6aacceaee811a80a9451f26cc1e8cba6ed56a49
ms.sourcegitcommit: 6cbdcb8606044ad7ab49a4e3c828c2dc3d50fcc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/09/2019
ms.locfileid: "36271376"
---
# <a name="plan-for-microsoft-365-government---gcc-high-deployments"></a>Plano para implantações altas do Microsoft 365 governo-GCC

Esta orientação é para os profissionais de ti que estão impulsionando implantações do Office 365 em entidades governamentais federais dos EUA ou outras entidades que lidam com os dados sujeitos a normas e requisitos governamentais, em que o uso do Microsoft 365 governo – o GCC High é adequado para atender a esses requisitos.

> [!NOTE]
> Se a sua organização já tiver atendido à Microsoft 365 governo-os requisitos de elegibilidade de alta qualificação e se foram aceitos no programa, você poderá ignorar as etapas 1 e 2 e ir diretamente para a etapa 3.

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-high-and-meets-eligibility-requirements"></a>Etapa 1. Determine se a sua organização precisa do Microsoft 365 governo-GCC alto e atenda aos requisitos de qualificação. 

O ambiente High Microsoft 365 governo-GCC oferece conformidade com os requisitos governamentais dos EUA para serviços de nuvem. Além de desfrutar dos recursos e funcionalidades do Office 365, as organizações se beneficiam dos seguintes recursos exclusivos para o governo da Microsoft 365 – GCC High:

- O conteúdo do cliente da sua organização é logicamente segregado do conteúdo do cliente nos serviços comerciais do Office 365 da Microsoft.
- O conteúdo do cliente da sua organização é armazenado nos Estados Unidos.
- O acesso ao conteúdo do cliente da sua organização está restrito ao pessoal da Microsoft em tela.
- Microsoft 365 governo – o GCC é compatível com certificações e certificações necessárias para clientes do setor público dos EUA.

Você pode encontrar mais informações sobre o governo Microsoft 365 – GCC High para clientes do governo dos EUA nos [planos do governo](https://products.office.com/government/compare-office-365-government-plans)dos EUA do Office 365, incluindo [os requisitos de qualificação](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

A [Descrição do serviço governo dos EUA do Office 365](https://docs.microsoft.com/en-us/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) descreve as vantagens da plataforma, que são centralizadas em requisitos de conformidade de reunião nos Estados Unidos.


> [!Tip]
> Talvez você queira transferir as tabelas de informações na descrição do serviço para uma pasta de trabalho do Excel e adicionar duas colunas: **pertinentes para minha organização y/n** e **atender às necessidades da minha organização y/n**. Em seguida, você pode revisar essa lista com seus colegas para confirmar que esse serviço atende às necessidades da sua organização.


|    |     |
|-----------|------------|
| ![Um ícone que representa os pontos de decisão](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se o Microsoft 365 governo-GCC High é apropriado para a sua organização.</li><li>Confirme se a sua organização atende aos requisitos de qualificação.</li></ul> |

> [!Note]
> O Microsoft 365 governo-GCC High só está disponível nos Estados Unidos. Os clientes do governo dos EUA podem escolher entre vários [planos governamentais do Office 365](https://products.office.com/en/government/compare-office-365-government-plans).

## <a name="step-2-apply-for-microsoft-365-government---gcc-high"></a>Etapa 2. Solicitar o Microsoft 365 governo-GCC alto

Decidisse que esse serviço é ideal para sua organização, inicie o processo de [aplicação para este serviço](https://products.office.com/government/eligibility-validation).


## <a name="step-3-understand-microsoft-365-government---gcc-high-default-security-settings"></a>Etapa 3. Compreenda as configurações de segurança padrão do governo do Microsoft 365-GCC High.

Recomendamos que você leve tempo para revisar cuidadosamente suas [configurações de administrador e de segurança](enable-features-office-365.md) antes de modificá-las e considerar o impacto sobre a conformidade antes de fazer qualquer alteração nas configurações de segurança padrão.

|    |     |
|-----------|------------|
| ![Um ícone que representa um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Decida se você precisará modificar qualquer uma das configurações de alta segurança do governo padrão do Microsoft 365, a solução para compreender primeiro o impacto de todas as alterações que você possa fazer.</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---gcc-high"></a>Etapa 4. Entender quais recursos do teams estão disponíveis no momento no Microsoft 365 governo-GCC alto

Para acomodar os requisitos de nossos clientes de nuvem governamental, há algumas diferenças entre as equipes do Microsoft 365 governo-GCC alta e as equipes nos planos empresariais. Consulte a tabela a seguir para ver os recursos disponíveis.

|                             | Recurso                     | GCC alto       |
|-----------------------------|-----------------------------|----------------|
| Polybase | Login | Disponível |
| | Presença | Disponível |
| | Presença unificada (Skype for Business e equipes unificadas) | Disponível |
| Atividades | Alimentação | Disponível |
|  | Minha atividade | Disponível |
| Chat | Conversa | Disponível |
| | Arquivos | Disponível |
| | Organograma | Disponível |
| | Atividades | Disponível |
| | Interoperabilidade (Teams 1:1-chat do Skype for Business) | Disponível |
| Microsoft Teams | Mensagem do canal | Disponível |
| | Arquivos de canal | Disponível |
| | Guia do OneNote | Na backlog do governo |
| | Enviar um canal por email | Não disponível |
| | Adicionar membro | Disponível |
| | Acesso de convidados | Na backlog do governo |
| Reuniões | Agendar reunião | Disponível |
| | Ingressar na reunião | Disponível |
| | Reunião de VoIP | Disponível |
| | Compartilhamento de área de trabalho | Disponível |
| | Conceder e assumir o controle no compartilhamento | Disponível |
| | Conectar-se a partir de uma sala de conferência | Disponível |
| | Junção anônima | Disponível |
| | Gravação na nuvem | Na backlog do governo |
| | Anotações da reunião | Disponível |
| | Transmitir reuniões | Na backlog do governo |
| | Reuniões federadas em nuvem (GCCH para GCCH) | Disponível |
| | Suporte a Surface Hub | Na backlog do governo |
| Chamadas | Contatos | Disponível |
| | Cliques | Disponível |
| | Caixa postal | Disponível |
| | Chamada VoIP | Disponível |
| | Skype para empresas-chamadas para equipes | Disponível |
| | Planos de Chamadas | Não disponível |
| | Conferência de áudio (permitindo que os participantes da reunião ingressem via PSTN) | Na backlog do governo |
| | Encaminhamento direto do sistema telefônico da Microsoft | Na backlog do governo |
| | Lobby para chamadores PSTN | Na backlog do governo |
| | Fila de chamadas | Na backlog do governo |
| | Suporte chefe e representante | Na backlog do governo |
| | Transferência consultiva e segura | Na backlog do governo |
| | Não incomodar | Na backlog do governo |
| | Toque distintivo | Na backlog do governo |
| | 1:1 para o encaminhamento de chamadas em grupo com o Teams, o Skype for Business e os participantes de PSTN | Na backlog do governo |
| | Encaminhar para o grupo | Na backlog do governo |
| | Transferir para chamada PSTN | Na backlog do governo |
| | Chamadas de emergência-planos de chamada | Na backlog do governo |
| | Suporte para telefones SIP certificados existentes | Na backlog do governo |
| | HID USB | Disponível |
| | Descoberta eletrônica para chamadas e reuniões | Disponível |
| | Atendedor automático da organização | Na backlog do governo |
| | Skype Consumer-suporte para chamadas de equipe | Não disponível |
| Arquivos | Alteração | Disponível |
| | Microsoft Teams | Disponível |
| Armazenadas | App Store | Não disponível |
| Pesquisa | Mensagens | Disponível |
| | Pessoas | Disponível |
| | Arquivos | Disponível |
| | Comandos de barra | Disponível |
| Conformidade | Pesquisa de conteúdo de conformidade | Disponível |
| | Tention | Disponível |
| | Pesquisa de log de auditoria | Disponível |
| | Controle legal | Disponível |
| | eDiscovery | Disponível |

|    |     |
|-----------|------------|
| ![Um ícone que representa um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Decida se o conjunto de recursos do teams atende às necessidades da sua organização.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Etapa 5. Plano de governança

Determine suas necessidades de governança e como você pode atendê-las. Vá para [plano de governança no Teams](plan-teams-governance.md) para obter mais informações.

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|Ponto de decisão |<ul><li>Determine e documente seus requisitos de governança, seguindo as diretrizes de [plano de controle no Teams](plan-teams-governance.md). </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>Etapa 6. Implantar equipes para colaboração

Depois de ter sido integrado ao Microsoft 365 governo – GCC High, você pode seguir a abordagem de implantação padrão do uso do [FastTrack](https://www.microsoft.com/fasttrack) e do seu parceiro escolhido para a integração do serviço.

Quando estiver pronto, implante o Microsoft Teams para [habilitar a colaboração em sua organização por meio de equipes e canais](teams-overview.md). Não deixe de entrar em contato com sua equipe de adoção e gerenciamento de mudanças ou especialistas do teams.
