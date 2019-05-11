---
title: Tarefas do Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1keywords: ms.teamsadmincenter.assignments.overview
description: Saiba como gerenciar atribuições no Centro de administração do Microsoft Teams em equipes educacional.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 263b9dda6929bd6956df803a33764634808cddf3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914019"
---
# <a name="assignments-in-teams-for-education"></a>Tarefas do Teams for Education

As atribuições são tarefas ou unidades de trabalho atribuído a um estudante ou membro da equipe em uma classe como parte de sua estudo. Você pode criar atribuições dentro de sua classe de equipes.

[Saiba mais sobre as atribuições](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Atribuições no Centro de administração do Microsoft Teams

Com as configurações de administração no Centro de administração do Microsoft Teams você pode ativar os seguintes recursos ou desativar esteja disponível para alunos e professores dentro da sua organização. Estas são as configurações relacionadas ao atribuições:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Resumo semanal de email responsável
Responsável emails são semanais emails enviados para os pais ou responsáveis dos alunos. Os e-mails irá conter informações sobre atribuições de semana anterior e para a semana de futura e serão enviados durante o final de semana. Os e-mails precisam ser atualizados pelos administradores usando o recurso de sincronização de dados da escola.

Essa configuração está desativado por padrão.

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
MakeCode é uma plataforma de codificação baseada em blocos que traz ciência da computação à vida para todos eles. 

Este é um produto de terceiros ou serviço que está sujeito a seus próprios termos e a diretiva de privacidade. Você é responsável por seu uso de quaisquer serviços e produtos de terceiros.

Essa configuração está desativado por padrão.

[Saiba mais sobre MakeCode](https://www.microsoft.com/${locale}/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

Turnitin é um serviço de detecção de plagiar. Este é um produto de terceiros ou serviço que está sujeito a seus próprios termos e a diretiva de privacidade. Você é responsável por seu uso de quaisquer serviços e produtos de terceiros.

Essa configuração está desativado por padrão.

Para permitir que Turnitin com êxito para a sua organização, você precisará já tiver uma assinatura de Turnitin. Você precisará inserir as seguintes informações adicionais, que podem ser encontradas no seu console de administração do Turnitin:

  * _TurnitinApiKey_: Este é um GUID de 32 caracteres encontrada no console de administração em integrações.
  * _TurnitinApiUrl_: esta é a URL HTTPS do seu console de administração do Turnitin.

Aqui estão algumas instruções para ajudá-lo a obter essas informações.

O TurnitinApiUrl é o endereço de host do seu console de administração.
![Localizando o TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin1.png)

Vá para a guia integrações e adicione uma integração.
![Localizando o TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin2.png)

O TurnitinApiKey receberá a você depois que você siga os prompts. Copie esta chave e colá-lo no Centro de administração do Microsoft Teams. 
![Localizando o TurnItInApiUrl](./educationImages/Assignments_mopo_turnitin3.png)

[Saiba mais sobre a integração entre o Turnitin e Teams da Microsoft](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)

[Saiba mais sobre Turnitin](https://www.turnitin.com/)
