---
title: 'Aplicativo pacientes para administradores do teams '
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
description: Saiba mais sobre o aplicativo pacientes para administradores do teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b86c180bc809fa10b261738ae5b324737006f541
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772182"
---
# <a name="patients-app-overview"></a>Visão geral do aplicativo de pacientes

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo pacientes foi desativado e substituído pelo [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Com listas, equipes de cuidado em sua organização de assistência médica podem criar listas de pacientes para cenários que vão desde rodadas e reuniões interdisciplinares de equipe até o monitoramento geral do paciente. Confira o modelo pacientes em listas para começar. Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md)

O aplicativo pacientes é um aplicativo do Microsoft Teams Store disponível para todos os usuários do teams. O aplicativo permite que as equipes de saúde dos pacientes que consistem em funcionários clínicos (por exemplo, as pessoas, os médicos, os funcionários sociais) podem auxiliar e revisar listas de pacientes para cenários que vão desde rodadas e reuniões interdisciplinares da equipe até o monitoramento geral do paciente.

O aplicativo tem dois modos:

- O modo conectado do EMR que se conecta ao EMRs por meio do FHIR. O aplicativo modo conectado do EMR permanece em uma visualização privada e clientes interessados ou administradores podem solicitar acesso ao aplicativo, descartando um email da Microsoft no [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) com informações sobre a sua organização Microsoft 365.
- O modo manual que permite que as equipes de saúde adicionem e tragam manualmente as informações dos pacientes. O aplicativo está disponível na App Store Teams para que os usuários finais Baixem na visualização privada. O aplicativo pode ser restrito a determinadas seções de usuários usando [políticas de configuração de aplicativo](../../teams-app-setup-policies.md) no Teams. Para obter acesso ao aplicativo, seu locatário precisa fazer parte do programa de adoção de tecnologia (toque). Envie-nos um email para [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) para iniciar o processo de solicitação de acesso.

## <a name="usage-example"></a>Exemplo de uso

Durante as sessões de arredondamento em cada mudança de médico, os clínicos reúnem-se na estação Nursing para discutir as atualizações mais recentes sobre o andamento com os pacientes.  Elas destacam as principais métricas críticas (não necessariamente médicas ou que são explícitas nos registros médicos dos pacientes) e garantem que o paciente esteja no caminho deslizante certo para a descarga com base em seu diagnóstico. Para arredondar esses pacientes, a enfermeira de cobrança define o aplicativo paciente em uma equipe em que todos os clínicos são adicionados e adiciona pacientes a uma lista de pacientes. Durante os rodadas, as hoje e outros responsáveis pelos participantes do paciente acessam o Microsoft Teams e o aplicativo pacientes em seus dispositivos móveis e atualizam informações relevantes dos pacientes em seus dispositivos e, em seguida, todos os outros na equipe de saúde podem ver essas atualizações e anotações e manter a sincronização. Duas vezes por dia, no início e no final de um turno, eles também têm reuniões de equipe multidisciplinares para passar pela lista de pacientes e usar o aplicativo pacientes para se basear e compartilhar informações sobre cada paciente usando o aplicativo pacientes em uma tela grande de exibição. Muitas vezes, alguns clínicos também podem discar para essas reuniões de equipes remotamente e ainda fazer parte da discussão.

## <a name="configure-patients-app"></a>Configurar o aplicativo pacientes

Para obter informações sobre como preparar seu ambiente para usar o aplicativo pacientes do modo EMR, consulte [integrando registros eletrônicos de saúde ao Microsoft Teams](patients-app.md). Você também precisará ver [gerenciar políticas de configuração do aplicativo no Microsoft Teams](../../teams-app-setup-policies.md) para habilitar o aplicativo pacientes para a sua organização.

Para obter informações sobre como os usuários finais podem acessar e instalar o aplicativo pacientes em uma equipe que eles possuem ou gerenciar, consulte [introdução aos pacientes do Microsoft Teams](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393).

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Perguntas frequentes (FAQ)

**Onde os dados do aplicativo pacientes são armazenados?**

Todos os dados inseridos pelos usuários finais no aplicativo pacientes, incluindo o esquema de coluna/campo, os dados reais inseridos nos itens de lista e lista (por exemplo, pacientes), são armazenados na infraestrutura do Exchange Online segura e compatível. Todos os dados são armazenados na caixa de correio do grupo associada à equipe. Essa arquitetura permite que o aplicativo pacientes atenda facilmente à residência de dados, ao suporte à nuvem governamental (futuramente) e a outros recursos de conformidade/proteção de informações, como suporte para descoberta eletrônica. O aplicativo pacientes opera em um escopo de equipe. Será necessário instalar uma instância do aplicativo por equipe.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**De onde eu posso adquirir o aplicativo pacientes?**

Se o aplicativo pacientes estiver habilitado para sua organização pelo administrador, qualquer usuário final poderá acessar a app Team Store e adicionar o aplicativo pacientes a uma equipe da qual eles são membros. Para obter mais informações, consulte [gerenciar políticas de configuração de aplicativos no Microsoft Teams](../../teams-app-setup-policies.md).

**Posso ter várias instâncias do aplicativo pacientes em uma equipe porque é assim que a minha unidade/unidade funciona?**

Atualmente, você só pode instalar uma instância do aplicativo pacientes para uma determinada equipe e somente no canal geral. No entanto, no aplicativo, várias listas podem ser criadas para lidar com cenários de vários canais ou isolamento/separação. Por padrão, todos os membros da equipe terão acesso à guia pacientes no canal geral. 

**Eu posso exportar todos os dados do aplicativo pacientes?**
No momento, mas este recurso estará disponível em breve. 

**Como esse aplicativo acomoda PHI, há auditoria para impedir o acesso não autorizado ou a conformidade com regulamentos?**

Sim, há. Cada ação de interface do usuário realizada por um usuário do Microsoft Teams no aplicativo pacientes é auditada e está disponível no centro de segurança e conformidade. Os detalhes são explicados nos [logs de auditoria do aplicativo pacientes](patients-audit.md).

## <a name="related-topics"></a>Tópicos relacionados

[Integração dos Registros Eletrônicos de Saúde no Microsoft Teams](patients-app.md)
