---
title: Plano para o Microsoft 365 Government ‒ implantações de GCC ‒ Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Orientação para profissionais de ti para conduzir as implantações do Office 365 em entidades que lidam com os dados sujeitos a normas do governo dos EUA
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e4228210fa7b6d9518fa060b2bdd555f434ed6f2
ms.sourcegitcommit: dc240b123efb03d5ab0545d650a973bf60d04506
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2019
ms.locfileid: "40069302"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Plano para implantações do governo Microsoft 365-GCC

Esta orientação é para os profissionais de ti que estão impulsionando implantações do Office 365 em entidades federais, estaduais, tribal ou outras entidades do governo dos EUA, que manipulam dados sujeitos a normas e requisitos governamentais, onde o uso do Microsoft 365 governo-GCC é adequado para atender a esses requisitos.

> [!NOTE]
> Se a sua organização já atendeu aos requisitos de qualificação do governo Microsoft 365 e se aplicou e foi aceito no programa, você pode ignorar as etapas 1 e 2 e ir diretamente para a etapa 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Etapa 1. Determine se a sua organização precisa do Microsoft 365 governo-GCC e atenda aos requisitos de qualificação. 

O ambiente Microsoft 365 governo-GCC fornece conformidade com os requisitos do governo dos EUA para serviços de nuvem, incluindo FedRAMP moderado e requisitos para justiça criminal e sistemas de informações federais fiscais (tipos de dados CJI e FTI).

Além de desfrutar dos recursos e funcionalidades do Office 365, as organizações se beneficiam dos seguintes recursos exclusivos do Microsoft 365 governo-GCC:

-   O conteúdo do cliente da sua organização é logicamente segregado do conteúdo do cliente nos serviços comerciais do Office 365 da Microsoft.
-   O conteúdo do cliente da sua organização é armazenado nos Estados Unidos.
-   O acesso ao conteúdo do cliente da sua organização está restrito ao pessoal da Microsoft em tela.
-   O Microsoft 365 governo-GCC está em conformidade com certificações e capacitações necessárias para clientes do setor público dos EUA.

Você pode encontrar mais informações sobre a oferta do Microsoft 365 governo-GCC para clientes do governo dos EUA em [planos do governo do Office 365](https://products.office.com/government/compare-office-365-government-plans), incluindo [requisitos de qualificação](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

A [Descrição do serviço governo dos EUA do Office 365](https://technet.microsoft.com/library/mt774581.aspx) descreve os benefícios da plataforma, que são centralizados em relação aos requisitos de conformidade nos Estados Unidos.

> [!Tip]
> Talvez você queira transferir as tabelas de informações na descrição do serviço para uma pasta de trabalho do Excel e adicionar duas colunas: **pertinentes para minha organização y/n** e **atender às necessidades da minha organização y/n**. Em seguida, você pode revisar essa lista com seus colegas para confirmar que esse serviço atende às necessidades da sua organização.

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se o Microsoft 365 governo-GCC é apropriado para sua organização.</li><li>Confirme se a sua organização atende aos requisitos de qualificação.</li></ul> |

> [!Note]
> Microsoft 365 governo-GCC só está disponível nos Estados Unidos. Os clientes do governo dos EUA podem escolher entre vários [planos governamentais do Office 365](https://products.office.com/en/government/compare-office-365-government-plans).


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Etapa 2. Solicitar o Microsoft 365 governo-GCC

Decidisse que esse serviço é ideal para sua organização, inicie o processo de [aplicação deste serviço aqui](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Etapa 3. Compreenda as configurações de segurança padrão do governo Microsoft 365-GCC.

Recomendamos que você leve tempo para revisar cuidadosamente suas [configurações de administrador e de segurança](enable-features-office-365.md) antes de modificá-las e considerar o impacto sobre a conformidade antes de fazer qualquer alteração nas configurações de segurança padrão.

|    |     |
|-----------|------------|
| ![Um ícone que representa um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Decida se você modificará qualquer uma das configurações de segurança do governo padrão da Microsoft 365, resolvendo para compreender primeiro o impacto de todas as alterações que você possa fazer.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Etapa 4. Compreenda quais recursos estão indisponíveis no momento ou desabilitados por padrão. 

Para acomodar os requisitos de nossos clientes de nuvem governamental, há algumas diferenças entre os planos Microsoft 365 governo-GCC e Enterprise. Consulte a tabela a seguir para ver os recursos disponíveis.

|                             | Recurso                     | GCC            |
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
| Teams | Mensagem do canal | Disponível |
| | Arquivos de canal | Disponível |
| | Guia do OneNote | Na backlog do governo |
| | Enviar um canal por email | Não disponível |
| | Adicionar membro | Disponível |
| | Acesso de convidados | Disponível |
| Reuniões | Agendar reunião | Disponível |
| | Ingressar na reunião | Disponível |
| | Reunião de VoIP | Disponível |
| | Compartilhamento de área de trabalho | Disponível |
| | Conceder e assumir o controle no compartilhamento | Disponível |
| | Conectar-se a partir de uma sala de conferência | Disponível |
| | Junção anônima | Disponível |
| | Gravação na nuvem | Disponível |
| | Anotações da reunião | Disponível |
| | Eventos ao vivo | Disponível |
| | Reuniões federadas | Disponível |
| | Suporte a Surface Hub | Disponível |
| Chamadas | Contatos | Disponível |
| | Cliques | Disponível |
| | Caixa postal | Disponível |
| | Chamada VoIP | Disponível |
| | Skype para empresas-chamadas para equipes | Disponível |
| | Planos de Chamadas | Disponível |
| | Conferência de áudio (permitindo que os participantes da reunião ingressem via PSTN) | Disponível |
| | Encaminhamento direto do sistema telefônico da Microsoft | Disponível |
| | Lobby para chamadores PSTN | Disponível |
| | Fila de chamadas | Disponível |
| | Suporte chefe e representante | Disponível |
| | Transferência consultiva e segura | Disponível |
| | Não incomodar | Disponível |
| | Toque distintivo | Disponível |
| | 1:1 para o encaminhamento de chamadas em grupo com o Teams, o Skype for Business e os participantes de PSTN | Disponível |
| | Encaminhar para o grupo | Disponível |
| | Transferir para chamada PSTN | Disponível |
| | Chamadas de emergência-planos de chamada | Disponível |
| | Suporte para telefones SIP certificados existentes | Disponível |
| | HID USB | Disponível |
| | Descoberta eletrônica para chamadas e reuniões | Disponível |
| | Atendedor automático da organização | Disponível |
| | Skype Consumer-suporte para chamadas de equipe | Disponível |
| Arquivos | Alteração | Disponível |
| | Microsoft Teams | Disponível |
| Armazenadas | App Store | Na backlog do governo |
| Pesquisa | Mensagens | Disponível |
| | Pessoas | Disponível |
| | Arquivos | Disponível |
| | Comandos de barra | Disponível |
| Conformidade | Pesquisa de conteúdo de conformidade | Disponível |
| | Tention | Disponível |
| | Pesquisa de log de auditoria | Disponível |
| | Controle legal | Disponível |
| | eDiscovery | Disponível |

> [!Note]

> Depois que outras cargas de trabalho estiverem totalmente disponíveis na nuvem GCC, elas serão disponibilizadas no Teams quando todo o trabalho adicional de integração for concluído.


|    |     |
|-----------|------------|
| ![Um ícone que representa um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Decida se o conjunto de recursos do teams atende às necessidades da sua organização.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Etapa 5. Plano de governança

Determine suas necessidades de governança e como você pode atendê-las. Vá para [plano de governança no Teams](plan-teams-governance.md) para obter mais informações.

|    |     |
|-----------|------------|
| ![Um ícone que representa um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Determine e documente seus requisitos de governança, seguindo as diretrizes de [plano de controle no Teams](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Etapa 6. Implantar equipes para colaboração

Depois de ter sido integrado ao Microsoft 365 governo – GCC, siga o caminho de implantação recomendado descrito em [como implantar o Microsoft Teams](How-to-roll-out-teams.md). Não deixe de entrar em contato com sua equipe de adoção e gerenciamento de mudanças e especialistas do teams.

Você também pode trabalhar com o [FastTrack](https://www.microsoft.com/fasttrack) ou o parceiro escolhido para onboard do serviço.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Etapa 7. Implantar equipes para reuniões e voz

Também é um ótimo momento para usar o Microsoft Teams com seu grupo de Stakeholder mais largo para começar a planejar reuniões e [recursos de voz na nuvem](cloud-voice-deployment.md).

