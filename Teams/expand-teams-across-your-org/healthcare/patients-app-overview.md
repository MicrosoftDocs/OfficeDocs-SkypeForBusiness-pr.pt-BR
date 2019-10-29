---
title: 'Aplicativo pacientes para administradores do teams '
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto: Microsoft Teams
ms.reviewer: anach
description: Aplicativo pacientes para administradores do teams
ms.openlocfilehash: 1ed3efc1aa5a6d3eb4554fca6ee3bd7cfe57f4c0
ms.sourcegitcommit: 25b6bf2c3050390cd668d2495ffcf31c44d0ff62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37749553"
---
# <a name="patients-app-overview"></a>Visão geral do aplicativo de pacientes

O aplicativo pacientes é um aplicativo do Microsoft Teams Store disponível para todos os usuários do teams. O aplicativo permite que as equipes de atendimento ao paciente que consistem em funcionários clínicos (por exemplo, retomadas, médicos, colegas de trabalho sociais) podem auxiliar e revisar listas de pacientes para cenários que vão desde rodadas e reuniões interdisciplinares da equipe até o monitoramento geral do paciente.   

O aplicativo tem dois modos: 

- O modo conectado do EMR que se conecta ao EMRs por meio do FHIR. O aplicativo modo conectado do EMR permanece em uma visualização privada e clientes interessados ou administradores podem solicitar acesso ao aplicativo, descartando um email da Microsoft no teamsforhealthcare@service.microsoft.com com informações sobre o locatário do Office 365. 
- O modo manual que permite às equipes de cuidado adicionar/trazer as informações do paciente manualmente. O aplicativo está disponível na loja de aplicativos do teams para que os usuários finais baixem por padrão e estejam em visualização pública. O aplicativo pode ser restrito a determinadas seções de usuários usando [políticas de configuração de aplicativos no Microsoft Teams](../../teams-app-setup-policies.md)



## <a name="usage-example"></a>Exemplo de uso

Durante as sessões de arredondamento em cada mudança de médico, os clínicos reúnem-se na estação Nursing para discutir as atualizações mais recentes sobre o andamento com os pacientes.  Elas destacam as principais métricas críticas (não necessariamente médicas ou que se encontram explícitas nos registros médicos dos pacientes) e garantem que o paciente esteja no caminho deslizante certo para a descarga eletrostática com base em seu diagnóstico. Para arredondar esses pacientes, a enfermeira de cobrança define o aplicativo paciente em uma equipe em que todos os clínicos são adicionados e adiciona pacientes a uma lista de pacientes. Durante os rodadas, as minhas mãos e os outros responsáveis pelos participantes do paciente acessarem o Microsoft Teams e o aplicativo pacientes em seus dispositivos móveis e atualizarão as informações relevantes dos pacientes em seus dispositivos e, em seguida, todos os outros na equipe de atendimento podem ver essas atualizações e anotações e Fique em sincronia. Duas vezes por dia, no início e no final de um turno, eles também têm reuniões de equipe displicinary para passar pela lista de pacientes e usar o aplicativo pacientes para se basear e compartilhar informações sobre cada paciente usando o aplicativo pacientes em uma tela grande de exibição. Muitas vezes, alguns clínicos também podem discar para essas reuniões de equipes remotamente e ainda fazer parte da discussão. 

## <a name="configure-patients-app"></a>Configurar o aplicativo pacientes

Para obter informações sobre como preparar seu ambiente para usar o aplicativo pacientes do modo EMR, consulte [integrando registros eletrônicos de saúde ao Microsoft Teams](patients-app.md). Você também precisará ver [gerenciar políticas de configuração do aplicativo no Microsoft Teams](../../teams-app-setup-policies.md) para habilitar o aplicativo pacientes para a sua organização.

<!-- For information on how your end users can access and install the Patients App to a team that they own or manage, you will need to see [End user documentation for the Patients App]() -->

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="related-topics"></a>Tópicos relacionados

[Integração dos Registros Eletrônicos de Saúde no Microsoft Teams](patients-app.md)
