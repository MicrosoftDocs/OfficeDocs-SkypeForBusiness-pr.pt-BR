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
ms.openlocfilehash: 64be355da30feb3c629569f583897353c21cfa37
ms.sourcegitcommit: 481d18b76304adfa340b5f1b2f1b7965e9ff4993
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2020
ms.locfileid: "49586614"
---
# <a name="assignments-in-teams-for-education"></a>Tarefas do Teams for Education

Os recursos de tarefas e notas no Teams for Education permitem que professores atribuam tarefas, trabalho ou testes a seus alunos. Educadores podem gerenciar cronogramas de atribuição, instruções, adicionar recursos para entrar, fazer uma classificação com reutilizáveis e muito mais. Eles também podem acompanhar a classe e o andamento individual do aluno na guia notas.

[Saiba mais sobre as tarefas e as notas no Teams for Education](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Para obter detalhes sobre as tarefas do Team em diferentes plataformas, consulte [recursos do teams por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integrações de atribuições no centro de administração do Microsoft Teams

Usando as configurações de administrador no centro de administração do Microsoft Teams, você pode ativar ou desativar recursos para educadores dentro da sua organização e de seus alunos. As configurações a seguir estão relacionadas às tarefas:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Resumo semanal do email do guardião


Os emails do Guardian são enviados a cada final de semana para pais ou tutores. O email contém informações sobre as tarefas da semana anterior e para a próxima semana. A sincronização pai e guardião pode ser configurada usando a [sincronização de dados da escola](https://docs.microsoft.com/schooldatasync/parent-contact-sync).

1. Importar informações de contato pai via sincronização de pai e guardião no SDS. Para obter instruções sobre como habilitar a sincronização de pais e guardiões, consulte [habilitando a sincronização de pai e guardião](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. Ative a configuração do guardião no centro de administração do Microsoft Teams, pois a configuração está desativada por padrão. Isso permitirá que os professores enviem um resumo semanal para você.

   > [!NOTE]
   > Os professores podem recusar o resumo desmarcando a configuração dentro de sua própria equipe de classe pessoal (**configurações de atribuição > emails pai/guardião**).

Para verificar se os pais receberão o email, os três itens a seguir devem ser verdadeiros:

 - Endereço de email anexado ao perfil do aluno no SDS e marcado como _pai_ ou _responsável_. Para obter detalhes, consulte o [formato de arquivo de sincronização pai e guardião](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).

 - Os alunos pertencem a pelo menos uma classe na qual o email não é desabilitado pelo professor nas [configurações de atribuição](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).

 - Os emails conterão informações sobre as atribuições que tiveram uma data de conclusão na semana anterior ou na próxima semana.

A configuração padrão para esse recurso é **desativada**.


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
O Microsoft MakeCode é uma plataforma de codificação baseada em blocos que leva a ciências da computação à vida para todos os alunos. 

O MakeCode é um produto da Microsoft que está sujeito aos [termos de uso e às políticas de](https://go.microsoft.com/fwlink/?LinkID=206977) [privacidade](https://go.microsoft.com/fwlink/?LinkId=521839) da Microsoft.

A configuração padrão para esse recurso é **desativada**.

Para habilitar as atribuições do MakeCode no Microsoft Teams, vá para o **centro de administração do teams**, navegue até a seção **tarefas** e ative a opção de alternância de **MakeCode.** Clique em **Salvar**. Aguarde algumas horas para que essas configurações entrem em vigor.

Para obter mais informações sobre como esse recurso funciona, consulte esta [demonstração em vídeo](https://makecode.com/blog/teams/teams-assignments).

[Saiba mais sobre o MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

O [TurnItIn](https://www.turnitin.com/) é um serviço de integridade acadêmica. Este é um produto ou serviço de terceiros sujeito aos seus próprios termos e políticas de privacidade. Você é responsável pelo uso de produtos e serviços de terceiros.

A configuração padrão para este recurso é **desativada**...

Para habilitar o TurnItIn para sua organização, você precisará de uma assinatura do TurnItIn. Em seguida, você pode inserir as informações a seguir, que podem ser encontradas no console de administração do TurnItIn:

  * **TurnitinApiKey**: é um GUID de caractere 32 encontrado no console de administração em integrações.
  * **TurnitinApiUrl**: esta é a URL https do seu console de administração do TurnItIn.

Aqui estão algumas instruções para ajudá-lo a obter essas informações.

O **TurnitinApiUrl** é o endereço de host do seu console de administração.
Exemplo `https://your-tenant-name.turnitin.com`

O console de administração é onde você pode criar uma integração e uma chave de API associada à integração.

Selecione **integrações** no menu do lado e, em seguida, selecione **Adicionar integração** e dê um nome à integração.

![Captura de tela mostrando como adicionar uma nova integração](./educationImages/Assignments_mopo_turnitin2.png)

O **TurnitinApiKey** será atribuído a você depois de seguir as instruções. Copie a chave da API e cole-a no centro de administração do Microsoft Teams.  Esta é a única vez que você pode ver a chave.

![Captura de tela mostrando a cópia da chave de API](./educationImages/Assignments_mopo_turnitin3.png)

Ao clicar no botão **salvar** no centro de administração para esta configuração, aguarde algumas horas para que essas configurações entrem em vigor.

