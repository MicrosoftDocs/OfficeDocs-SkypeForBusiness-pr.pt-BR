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
description: Saiba como gerenciar atribuições no centro de administração do Microsoft Teams no Teams for Education.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 188f4398136c2939ad2a84d75ab27942a5a4593b
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433427"
---
# <a name="assignments-in-teams-for-education"></a>Tarefas do Teams for Education

As atribuições são tarefas ou unidades de trabalho atribuídas a um membro do aluno ou da equipe em uma classe como parte do estudo. Você pode criar tarefas dentro da classe Teams.

[Saiba mais sobre as tarefas](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Tarefas no centro de administração do Microsoft Teams

Com as configurações de administrador no centro de administração do Microsoft Teams, você pode ativar ou desativar os recursos a seguir para estar disponível para alunos e professores em sua organização. As configurações a seguir estão relacionadas às tarefas:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Resumo semanal do email do guardião
Emails do guardião são e-mails semanais enviados para pais ou tutores dos alunos. Os emails contêm informações sobre as tarefas da semana anterior e para a próxima semana e serão enviados pelo final de semana. Os emails precisam ser atualizados pelos administradores usando o recurso de sincronização de dados da escola.

Essa configuração está desativada por padrão.

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
O MakeCode é uma plataforma de codificação baseada em blocos que dá vida a toda a sua ciência ao computador para todos os alunos. 

Este é um produto ou serviço de terceiros sujeito aos seus próprios termos e políticas de privacidade. Você é responsável pelo uso de produtos e serviços de terceiros.

Essa configuração está desativada por padrão.

[Saiba mais sobre o MakeCode](https://www.microsoft.com/${locale}/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

TurnItIn é um serviço de detecção de plagiarism. Este é um produto ou serviço de terceiros sujeito aos seus próprios termos e políticas de privacidade. Você é responsável pelo uso de produtos e serviços de terceiros.

Essa configuração está desativada por padrão.

Para habilitar o TurnItIn com êxito para sua organização, você precisará ter uma assinatura do TurnItIn. Será necessário inserir as seguintes informações adicionais, que podem ser encontradas no console de administração do TurnItIn:

  * _TurnitinApiKey_: é um GUID de caractere 32 encontrado no console de administração em integrações.
  * _TurnitinApiUrl_: esta é a URL https do seu console de administração do TurnItIn.

Aqui estão algumas instruções para ajudá-lo a obter essas informações.

O TurnitinApiUrl é o endereço de host do seu console de administração.
![Captura de tela mostrando o endereço do host](./educationImages/Assignments_mopo_turnitin1.png)

Vá para a guia integrações e adicione uma integração.
![Captura de tela mostrando a adição de uma nova integração](./educationImages/Assignments_mopo_turnitin2.png)

O TurnitinApiKey será atribuído a você depois de seguir as instruções. Copie essa chave e cole-a no centro de administração do Microsoft Teams. 
![Captura de tela mostrando a cópia da chave de API](./educationImages/Assignments_mopo_turnitin3.png)

[Saiba mais sobre a integração entre o TurnItIn e o Microsoft Teams](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)

[Saiba mais sobre o TurnItIn](https://www.turnitin.com/)
