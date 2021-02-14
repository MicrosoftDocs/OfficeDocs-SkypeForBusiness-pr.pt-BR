---
title: 'Aplicativo Pacientes para administradores do Teams '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Saiba mais sobre o aplicativo Pacientes para administradores do Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 92bc7581610abf1dc8baab17d2e9d23abb6c6fd3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803499"
---
# <a name="patients-app-overview"></a>Visão geral do aplicativo de pacientes

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo Pacientes foi retirado e substituído pelo aplicativo [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Os dados do aplicativo Pacientes são armazenados na caixa de correio de grupo do grupo do Office 365 que faz o back-back da equipe. Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário. Os usuários podem criar suas listas de novo usando o [aplicativo Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Com as Listas, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam de reuniões de equipes de turnos e de atendimento a monitoramento geral de pacientes. Confira o modelo Pacientes em Listas para começar. Para saber mais sobre como gerenciar o aplicativo Listas em sua organização, consulte [Gerenciar o aplicativo Listas.](../../manage-lists-app.md)

O aplicativo Pacientes é um aplicativo da Microsoft Teams Store disponível para todos os usuários do Teams. O aplicativo habilita equipes de saúde dos pacientes que consistem em trabalhadores clínicos (por exemplo, médicos, médicos, assistentes sociais) podem analisar e analisar listas de pacientes para cenários que variam de reuniões de equipes de turnos e merários até o monitoramento geral dos pacientes.

O aplicativo tem dois modos:

- O modo conectado a EMR que se conecta a EMRs por meio de FHIR. O aplicativo modo Conectado ao [EMR](mailto:teamsforhealthcare@service.microsoft.com) permanece em visualização privada, e os administradores ou clientes interessados podem solicitar acesso ao aplicativo, soltando um email da Microsoft no teamsforhealthcare@service.microsoft.com com informações sobre sua organização do Microsoft 365.
- O modo manual que permite que as equipes de saúde adicionem/trazem manualmente informações dos pacientes. O aplicativo está disponível na loja de aplicativos do Teams para que os usuários finais baixem em visualização privada. O aplicativo pode ser restrito a determinadas seções de usuários que usam políticas [de configuração de aplicativos](../../teams-app-setup-policies.md) no Teams. Para obter acesso ao aplicativo, seu locatário precisa fazer parte do Programa de Adoção de Tecnologia (TAP). Envie-nos um email no [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) para iniciar o processo para solicitar acesso.

## <a name="usage-example"></a>Exemplo de uso

Durante as sessões de arredondamento em todos os turnos em alas médicas, os médicos se reúnem na estação de repouso para discutir as atualizações mais recentes sobre o progresso com pacientes na escola.  Eles destacam as principais métricas críticas (não necessariamente médicas ou explícitas nos registros médicos dos pacientes) e garantem que o paciente está no caminho certo para a quitação com base no diagnóstico. Para arredondar esses pacientes, a enfermeira responsável configura o aplicativo paciente em uma equipe onde todos os médicos são adicionados e adicionam pacientes a uma lista de pacientes. Durante as voltas, as pacientes e os demais responsáveis pelos cuidados do paciente acessam o Microsoft Teams e o aplicativo Pacientes em seus dispositivos móveis e atualizam informações relevantes dos pacientes em seus dispositivos e, em seguida, todos na equipe de saúde podem ver essas atualizações e anotações e permanecer em sincronia. Duas vezes por dia, no início e no final de um turno, eles também têm reuniões de equipe multi-disciplina para passar pela lista de pacientes e usar o aplicativo Pacientes para se basear e compartilhar informações sobre cada paciente usando o aplicativo Pacientes em uma tela de exibição grande. Muitas vezes, determinados médicos também podem discar para essas reuniões do Teams remotamente e ainda fazer parte da discussão.

## <a name="configure-patients-app"></a>Configurar o aplicativo Pacientes

Para obter informações sobre como preparar seu ambiente para usar o aplicativo Pacientes do modo EMR, consulte Integrando registros de saúde [eletrônicos no Microsoft Teams.](patients-app.md) Você também precisará ver Gerenciar políticas de configuração [de aplicativos no Microsoft Teams](../../teams-app-setup-policies.md) para habilitar o aplicativo Pacientes para sua organização.

Para obter informações sobre como os usuários finais podem acessar e instalar o aplicativo Pacientes em uma equipe que eles têm ou gerenciam, consulte Começar a usar os Pacientes [do Microsoft Teams.](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Perguntas frequentes (perguntas frequentes)

**Onde os dados do aplicativo Pacientes são armazenados?**

Todos os dados inseridos pelos usuários finais no aplicativo Pacientes, incluindo o esquema de coluna/campo, os dados reais inseridos na lista e itens de lista (ou seja, pacientes), são armazenados na infraestrutura segura e compatível do Exchange Online. Todos os dados são armazenados na caixa de correio do grupo associada à equipe. Essa arquitetura permite que o aplicativo Pacientes cumpra facilmente a residência de dados, o suporte na nuvem governamental (futuramente) e outros recursos de proteção de informações/conformidade, como o suporte à Descoberta E. O aplicativo Pacientes opera em um escopo de equipe. Você precisará instalar uma instância do aplicativo por equipe.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**De onde posso adquirir o aplicativo Pacientes?**

Se o aplicativo Pacientes estiver habilitado para sua organização pelo administrador, qualquer usuário final poderá ir para a loja de aplicativos do Teams e adicionar o aplicativo Pacientes a uma equipe da onde ele é membro. Para obter mais informações, consulte [Gerenciar políticas de configuração de aplicativos no Microsoft Teams.](../../teams-app-setup-policies.md)

**Posso ter várias instâncias do aplicativo Pacientes em uma equipe porque é assim que minha unidade/unidade opera?**

Atualmente, você só pode instalar uma instância do aplicativo Pacientes para uma determinada equipe e somente no canal geral. No entanto, no aplicativo, várias listas podem ser criadas para lidar com cenários de vários canais ou isolamento/separação. Por padrão, todos os membros da equipe terão acesso à guia Pacientes no canal geral. 

**Posso exportar todos os dados do aplicativo Pacientes?**
Não no momento, mas este recurso estará em breve. 

**Como este aplicativo acomoda PHI, há auditoria para impedir o acesso não autorizado ou a conformidade com os regulamentos?**

Sim, há. Todas as ações da interface do usuário realizadas por um usuário do Microsoft Teams no aplicativo Pacientes são auditadas e estão disponíveis no centro de segurança e conformidade. Os detalhes são explicados nos [logs de auditoria do aplicativo Pacientes.](patients-audit.md)

## <a name="related-topics"></a>Tópicos relacionados

[Integração dos Registros Eletrônicos de Saúde no Microsoft Teams](patients-app.md)
