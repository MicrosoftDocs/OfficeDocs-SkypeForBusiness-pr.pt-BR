---
title: Tarefas do Teams
author: cichur
ms.author: v-mahoffman
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
description: Saiba como gerenciar atribuições no Microsoft Teams de administração no Teams para Educação.
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c2dbc67fdbc55c9ff2a7b2e16cb0957886de3dd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758303"
---
# <a name="assignments-in-teams-for-education"></a>Tarefas do Teams for Education

Os recursos Atribuições e Notas no Teams para Educação permitem que os educadores atribuam tarefas, trabalho ou testes aos seus alunos. Os educadores podem gerenciar cronogramas de atribuição, instruções, adicionar recursos para a atribuição, notas com rubricas e muito mais. Eles também podem acompanhar o progresso da classe e do aluno individual na guia Notas.

[Saiba mais sobre atribuições e notas em Teams para Educação](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).

> [!Note]
> Para obter detalhes sobre Teams atribuições em diferentes plataformas, [consulte Teams recursos por plataforma](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Integrações de atribuições no Microsoft Teams de administração

Usando as configurações de administrador no Microsoft Teams de administração, você pode ativar ou desativar recursos para educadores em sua organização e seus alunos. Veja a seguir as configurações relacionadas a atribuições:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>Resumo semanal de email do guardião


Emails de tutor são enviados a cada fim de semana para pais ou responsáveis. O email contém informações sobre atribuições da semana anterior e da próxima semana. A Sincronização pai e guardião pode ser configurada usando [School Data Sync](/schooldatasync/parent-contact-sync).

1. Importar informações de contato pai por meio da Sincronização pai e guardião no SDS. Para obter instruções sobre como habilitar a sincronização pai e guardião, consulte [Enableing Parent and Guardian Sync](/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).

2. A opção Ativar a Configuração do Guardião no Microsoft Teams de administração, já que a configuração está desabilitada por padrão. Isso permitirá que os professores enviem um resumo semanal.

   > [!NOTE]
   > Os professores podem optar por não participar do resumo, desmarcando a configuração dentro de sua própria equipe de classe pessoal (**Assignment Configurações > Parent/Guardian Emails**).

Para verificar se os Pais receberão o email, os três itens a seguir devem ser verdadeiros:

 - Endereço de email anexado ao perfil do aluno no SDS e marcado como _Pai_ ou _Guardião._ Para obter detalhes, consulte [Parent and Guardian Sync File Format](/schooldatasync/parent-contact-sync-file-format).

 - Os alunos pertencem a pelo menos uma classe na qual o email não está desabilitado pelo professor nas configurações [de atribuição.](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)

 - Os emails conterão informações sobre atribuições que tinham uma data de vencimento na semana anterior ou na próxima semana.

A configuração padrão para esse recurso é - **Off**.


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
O Microsoft MakeCode é uma plataforma de codificação baseada em blocos que dá vida à ciência da computação para todos os alunos. 

MakeCode é um produto da Microsoft que está sujeito aos termos de uso [e](https://go.microsoft.com/fwlink/?LinkID=206977) políticas de privacidade [da](https://go.microsoft.com/fwlink/?LinkId=521839) Microsoft.

A configuração padrão para esse recurso é - **Off**.

Para habilitar as Teams MakeCode no Teams, vá para o Centro  de Administração Teams, navegue até **a** seção Atribuições e ative a opção de alternância MakeCode **como** Ativado. Clique em **Salvar**. Permita algumas horas para que essas configurações entre em vigor.

Para obter mais informações sobre como esse recurso funciona, consulte esta [demonstração de vídeo](https://makecode.com/blog/teams/teams-assignments).

[Saiba mais sobre MakeCode](https://aka.ms/makecode).

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin é](https://www.turnitin.com/) um serviço de integridade acadêmica. Esse é um produto ou serviço de terceiros que está sujeito aos seus próprios termos e política de privacidade. Você é responsável pelo uso de quaisquer produtos e serviços de terceiros.

A configuração padrão para esse recurso é - **Off**..

Para habilitar o Turnitin para sua organização, você precisará de uma assinatura turnitin. Em seguida, você pode inserir as seguintes informações, que podem ser encontradas no console de administração do Turnitin:

  * **TurnitinApiKey**: Este é um GUID de 32 caracteres encontrado no console de administração em Integrações.
  * **TurnitinApiUrl**: Esta é a URL HTTPS do console de administração turnitin.

Aqui estão algumas instruções para ajudá-lo a obter essas informações.

**TurnitinApiUrl** é o endereço host do console de administração.
Exemplo: `https://your-tenant-name.turnitin.com`

O console de administrador é onde você pode criar uma integração e uma chave de API associada à integração.

Selecione **Integrações** no menu lateral e selecione **Adicionar Integração** e dê um nome à integração.

![Captura de tela mostrando a adição de uma nova integração.](./educationImages/Assignments_mopo_turnitin2.png)

O **TurnitinApiKey** será dado a você depois de seguir os prompts. Copie a chave da API e a colar no centro de Microsoft Teams de administração.  Esta é a única hora em que você pode exibir a chave.

![Captura de tela mostrando a cópia da chave da API.](./educationImages/Assignments_mopo_turnitin3.png)

Ao clicar no **botão Salvar** no centro de administração para essa configuração, permita algumas horas para que essas configurações entre em vigor.

### <a name="removing-assignments-and-grades"></a>Removendo atribuições e notas
Você pode usar Teams para remover atribuições e notas para um usuário específico ou para todo o locatário. 

Para remover atribuições e notas de um  usuário individual, vá para o Centro de Administração Teams e navegue até Teams **aplicativos > Políticas** de permissão para criar uma nova definição de política de permissão de aplicativo.  Ao criar a nova definição de  política, desmarque a política de aplicativos da **Microsoft** como Bloquear **aplicativos específicos** e permita que todos os outros e adicione atribuições à lista de aplicativos bloqueados. Depois que a nova definição de política for salva, atribua-a aos usuários apropriados.

Para remover atribuições e notas de todo o locatário, vá para o Centro de Administração **Teams,** navegue até Teams **aplicativos > Gerenciar** aplicativos e pesquise e selecione Atribuições na lista de **aplicativos.** Altere a configuração de status na página Configurações do aplicativo de atribuição como _Bloqueado_. 
