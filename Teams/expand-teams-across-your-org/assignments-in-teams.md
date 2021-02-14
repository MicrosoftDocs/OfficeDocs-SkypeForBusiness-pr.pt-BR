---
title: Tarefas do Teams
author: cichur
ms.author: v-cichur
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
description: Saiba como gerenciar tarefas no Centro de administração do Microsoft Teams no Teams para Educação.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: f283a4fb2d49778f4b0e8b31f46dada46f900e6f
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616905"
---
# <a name="assignments-in-teams-for-education"></a>Tarefas do Teams for Education

Os recursos tarefas e notas no Teams for Education permitem que os educadores atribuam tarefas, trabalhos ou testes aos alunos. Os educadores podem gerenciar cronogramas de tarefas, instruções, adicionar recursos para entregar, dar nota com orientações e muito mais. Eles também podem acompanhar o progresso das aulas e dos alunos individuais na guia Notas.

[Saiba mais sobre tarefas e notas no Teams for Education.](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

> [!Note]
> Para obter detalhes sobre as atribuições do Teams em diferentes plataformas, consulte os [recursos do Teams por plataforma.](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integrações de atribuições no Centro de administração do Microsoft Teams

Usando as configurações de administração no Centro de administração do Microsoft Teams, você pode ativar ou desativar recursos para educadores de sua organização e seus alunos. Veja a seguir as configurações relacionadas às Tarefas:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Resumo semanal de email do responsável


Emails de tutores são enviados todos os finais de semana para pais ou tutores. O email contém informações sobre as tarefas da semana anterior e da próxima semana. A Sincronização de Pais e Tutores pode ser configurada usando [o School Data Sync.](https://docs.microsoft.com/schooldatasync/parent-contact-sync)

1. Importe informações de contato pai por meio da Sincronização de Pais e Tutores no SDS. Para obter instruções sobre como habilitar a Sincronização de Pais e Tutores, consulte Habilitar a Sincronização [de Pais e Tutores.](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)

2. A ativar a Configuração do Tutor no Centro de administração do Microsoft Teams, uma vez que a configuração está desabilitada por padrão. Isso permitirá que os professores enviem um resumo semanal.

   > [!NOTE]
   > Os professores podem optar por não digerir desmarcando a configuração dentro de sua própria equipe de classe pessoal ( Configurações de Tarefa > Emails de **pais/tutores).**

Para verificar se os pais receberão o email, os três itens a seguir devem ser verdadeiros:

 - Endereço de email anexado ao perfil do aluno no SDS e marcado como _pai_ ou _responsável._ Para obter detalhes, consulte [o Formato de Arquivo de Sincronização de Pais e Tutores.](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)

 - Os alunos pertencem a pelo menos uma classe na qual o email não é desabilitado pelo professor nas configurações [de tarefa.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)

 - Os emails conterão informações sobre tarefas que tinham uma data de vencimento na semana anterior ou na próxima semana.

A configuração padrão para esse recurso é – **Desligado.**


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
O Microsoft MakeCode é uma plataforma de codificação baseada em blocos que dá vida à ciência do computador para todos os alunos. 

MakeCode é um produto da Microsoft que está sujeito aos termos [de uso e](https://go.microsoft.com/fwlink/?LinkID=206977) políticas de privacidade [da](https://go.microsoft.com/fwlink/?LinkId=521839) Microsoft.

A configuração padrão para esse recurso é – **Desligado.**

Para habilitar as atribuições do MakeCode no Teams, vá para o Centro de Administração do **Teams,** navegue até a seção Tarefas e ative a opção de alternância  MakeCode.  Clique em **Salvar**. Permita que algumas horas para que essas configurações entre em vigor.

Para obter mais informações sobre como esse recurso funciona, consulte esta [demonstração em vídeo.](https://makecode.com/blog/teams/teams-assignments)

[Saiba mais sobre MakeCode.](https://aka.ms/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin é](https://www.turnitin.com/) um serviço de integridade acadêmica. Este é um produto ou serviço de terceiros que está sujeito aos seus próprios termos e política de privacidade. Você é responsável pelo uso de produtos e serviços de terceiros.

A configuração padrão para esse recurso é - **Off**..

Para habilitar o Turnitin para sua organização, você precisará de uma assinatura do Turnitin. Em seguida, você pode inserir as seguintes informações, que podem ser encontradas em seu console de administração turnitin:

  * **TurnitinApiKey:** este é um GUID de 32 caracteres encontrado no console de administração em Integrações.
  * **TurnitinApiUrl:** esta é a URL HTTPS do seu console de administração Turnitin.

Aqui estão algumas instruções para ajudá-lo a obter essas informações.

O **TurnitinApiUrl** é o endereço de host do console de administração.
Exemplo: `https://your-tenant-name.turnitin.com`

O console de administração é onde você pode criar uma integração e uma chave da API associada à integração.

Selecione **Integrações** no menu lateral, selecione **Adicionar Integração** e dê um nome à integração.

![Captura de tela mostrando a adição de uma nova integração](./educationImages/Assignments_mopo_turnitin2.png)

O **TurnitinApiKey** será entregue a você depois que você seguir as solicitações. Copie a chave da API e a colar no Centro de administração do Microsoft Teams.  Esta é a única vez que você pode exibir a chave.

![Captura de tela mostrando a cópia da chave da API](./educationImages/Assignments_mopo_turnitin3.png)

Ao clicar no **botão Salvar** no centro de administração para essa configuração, deixe algumas horas para que essas configurações entre em vigor.

