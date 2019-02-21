---
title: Configurar a licença de Telefone de Área Comum para o Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 12/13/2018
ms.reviewer: kponnus
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba como configurar os telefones de área comum para lobbies, áreas de recepção e salas de conferência '
ms.openlocfilehash: b7fb997a8e9367c4a3b8629f037ad79871b64b25
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2019
ms.locfileid: "30121040"
---
# <a name="set-up-the-common-area-phone-license-for-microsoft-teams"></a>Configurar a licença de Telefone de Área Comum para o Microsoft Teams

Um telefone de área comum geralmente é colocado em uma área de como um lobby ou outro que está disponível para muitas pessoas para fazer uma chamada; Por exemplo, uma recepção área, lobby ou conferência telefônica. Telefones de área comum são configurados como dispositivos em vez de usuários e podem entrar automaticamente em uma rede.

Nas etapas abaixo, podemos ajudá-lo a configurar uma conta para o sistema telefônico implantar telefones de área comum para sua organização. Para uma sala de reunião mais completa experiência, incluindo serviços de audioconferência, considere adquirir a licença de sala de reunião dedicada com uma reunião do dispositivo de sala. 

As primeiras coisas que você precisa fazer são compra uma licença de telefone de área comum (COBRIR) e certifique-se de que você tiver um telefone de certificados. Para procurar e saber mais sobre certificados telefones, vá para [dispositivos de equipes da Microsoft](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1). 

## <a name="step-1---buy-the-licenses"></a>Etapa 1 - Compre as licenças

1. No Centro de administração do Office 365, vá para **faturamento** > **Serviços de compra** e, em seguida, expanda **outros planos**.

    ![Captura de tela mostrando os blocos de telefone de área comum](media/set-up-common-area-phone-image1.png)

2. Selecione o **telefone de área comum** > **Compre agora**.

3. Na página de **check-out** , clique em **Comprar agora**.

4. Expanda **inscrições de complemento** e clique em para adquirir um plano de chamada. Escolha a **domésticas chamar plano** ou **plano de chamada nacionais e internacional**.

> [!NOTE]
> Você não precisa de uma licença do Sistema de Telefonia. Ela está incluída na licença do Telefone da Área Comum.

Para obter mais informações sobre licenças, consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

## <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Etapa 2 - Criar uma nova conta de usuário para o telefone e atribuir as licenças

1. No Centro de administração do Office 365, vá para **usuários** > **usuários ativos** > **Adicionar um usuário**.

2. Insira um nome de usuário como "Main" para o primeiro nome e "Recepção" para o segundo nome.

3. Insira um nome de exibição se ele não gerar automaticamente um como "Main recepção".

4. Insira um nome de usuário, como "MainReception" ou "Mainlobby".

5. Para telefones de área comum, talvez você queira definir uma senha manualmente ou ter a mesma senha para todos os telefones de área comum. Além disso, você pode achar sobre desmarcar a caixa de seleção **tornar este usuário alterar suas senhas quando eles entrarem pela primeira vez** .

6. Atribua as licenças para o usuário. Na mesma página, clique para expandir as **Licenças de produto**. Ligue o telefone de área comum e escolha um **Domésticas chamar planejar** ou um **nacionais e internacionais chamar planejar**. 

    ![Atribuição de licença captura de tela mostrando](media/set-up-common-area-phone-image2.png)

Para obter mais informações, consulte [Adicionar um usuário](https://docs.microsoft.com/office365/admin/add-users/add-users?redirectSourcePath=%252farticle%252f1970f7d6-03b5-442f-b385-5880b9c256ec&view=o365-worldwide).

## <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Etapa 3 - Atribuir um número de telefone à conta de usuário do Telefone de Área Comum

Use o Skype para centro de administração de negócios para atribuir um número ao usuário.

1. No Centro de administração do Microsoft 365, selecione **Admin centrais** > **& equipes Skype** > **portal herdada**.

2. No Skype para centro de administração de negócios, selecione **voz** > **números de telefone**.

3.  Selecione um número na lista de números de telefone e clique em **Atribuir**.

4. Na página **atribuir** , na caixa de usuário de voz, digite o nome do usuário que estarão usando o telefone e selecione o usuário na lista suspensa **Selecione um usuário de voz** .

5. Na página, você precisa adicionar um endereço de emergência. Escolha **pesquisa por cidade**, **pesquisa por descrição**ou **pesquisa por local** na lista suspensa e, em seguida, insira a cidade, descrição ou local na caixa de texto. Depois que você pode pesquisar, procure em **Selecione endereço de emergência** para escolher o certo para você.

6. Clique em **Salvar** e seu usuário ficará assim:

   ![Atribuição de licença captura de tela mostrando](media/set-up-common-area-phone-image3.png)

> [!NOTE]
> Os usuários serão exibidas apenas se eles têm uma licença de sistema telefônico aplicada. Quando fizer isso, pode levar um tempo para que o usuário apareça na lista.

Para obter mais informações, consulte [Getting números de telefone para seus usuários](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users).

Você também pode aproveitar o seu número de telefone que você tenha com outra operadora e "porta" ou transferi-la para o Office 365. Consulte [transferir os números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).


