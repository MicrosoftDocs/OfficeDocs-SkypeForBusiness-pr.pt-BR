---
title: Tarefas do Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Saiba como gerenciar atribuições no centro de administração do Microsoft Teams no Teams for Education.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd2cef56b4b59461ea1eeb5028c6c77a92e20500
ms.sourcegitcommit: 491c44b6a9b30faaf4d73394969f4a0587362830
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47820625"
---
# <a name="assignments-in-teams-for-education"></a>Tarefas do Teams for Education

As atribuições são tarefas ou unidades de trabalho atribuídas a um membro do aluno ou da equipe em uma classe como parte do estudo. Você pode criar tarefas dentro da classe Teams.

[Saiba mais sobre as tarefas](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> Para obter detalhes sobre as tarefas do Team em diferentes plataformas, consulte [recursos do teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Tarefas no centro de administração do Microsoft Teams

Com as configurações de administrador no centro de administração do Microsoft Teams, você pode ativar ou desativar os recursos a seguir para estar disponível para alunos e professores em sua organização. As configurações a seguir estão relacionadas às tarefas:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Resumo semanal do email do guardião

Emails do guardião são e-mails semanais enviados para pais ou tutores dos alunos. Os emails contêm informações sobre as tarefas da semana anterior e para a próxima semana e serão enviados pelo final de semana. Os emails precisam ser atualizados pelos administradores usando o recurso de sincronização de dados da escola.

Essa configuração está desativada por padrão.

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
O Microsoft MakeCode é uma plataforma de codificação baseada em blocos que leva a ciências da computação à vida para todos os alunos. 

O MakeCode é um produto da Microsoft que está sujeito aos [termos de uso e às políticas de](https://go.microsoft.com/fwlink/?LinkID=206977) [privacidade](https://go.microsoft.com/fwlink/?LinkId=521839) da Microsoft.

Essa configuração está desativada por padrão. Para habilitar as tarefas do MakeCode no Teams, no **centro de administração do teams**, navegue até a seção **tarefas** e ative a opção de alternância de **MakeCode.** Clique em **salvar** e aguarde algumas horas para que as configurações entrem em vigor.

Para obter mais informações sobre como esse recurso funciona, consulte esta [demonstração em vídeo](https://makecode.com/blog/teams/teams-assignments).

[Saiba mais sobre o MakeCode](https://aka.ms/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

TurnItIn é um serviço de detecção de plagiarism. Este é um produto ou serviço de terceiros sujeito aos seus próprios termos e políticas de privacidade. Você é responsável pelo uso de produtos e serviços de terceiros.

Essa configuração está desativada por padrão.

Para habilitar o TurnItIn com êxito para sua organização, você precisará ter uma assinatura do TurnItIn. Será necessário inserir as seguintes informações adicionais, que podem ser encontradas no console de administração do TurnItIn:

  * _TurnitinApiKey_: é um GUID de caractere 32 encontrado no console de administração em integrações.
  * _TurnitinApiUrl_: esta é a URL https do seu console de administração do TurnItIn.

Aqui estão algumas instruções para ajudá-lo a obter essas informações.

O TurnitinApiUrl é o endereço de host do seu console de administração.
Exemplo. `https://your-tenant-name.turnitin.com`

O console de administração é onde você pode criar uma integração e uma chave de API associada à integração.

Selecione **integrações** no menu do lado e, em seguida, selecione **Adicionar integração** e dê um nome à integração.
![Captura de tela mostrando como adicionar uma nova integração](./educationImages/Assignments_mopo_turnitin2.png)

O TurnitinApiKey será atribuído a você depois de seguir as instruções. Copie a chave da API e cole-a no centro de administração do Microsoft Teams.  Esta é a única vez que você pode ver a chave.
![Captura de tela mostrando a cópia da chave de API](./educationImages/Assignments_mopo_turnitin3.png)

Ao clicar no botão **salvar** no centro de administração para esta configuração, aguarde algumas horas para que essas configurações entrem em vigor.

Pronto para começar a usar a integração do TurnItIn no Microsoft Teams? Inscreva-se para o [programa de acesso antecipado](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).
