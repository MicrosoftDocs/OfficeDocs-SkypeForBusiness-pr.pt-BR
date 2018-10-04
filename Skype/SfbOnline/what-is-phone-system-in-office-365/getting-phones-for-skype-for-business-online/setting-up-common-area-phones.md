---
title: Configurar telefones de área comum
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Conheça as etapas de implantação para obter o firmware correto, atualizá-la, se necessário, atribuir licenças e definir configurações para telefones de área comum.
ms.openlocfilehash: 3faa66235f3c3364a0da6560a6dc52daa252915b
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370671"
---
# <a name="set-up-common-area-phones"></a>Configurar telefones de área comum
A common area phone (CAP) is typically placed in an area like a lobby or another area that is available to a lot of people. For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically sign into a network. In the steps below, we’ll help you set up an account for Phone System with Calling Plans so you can deploy these types of phones for your organization.

## <a name="prerequisites-for-common-area-phones"></a>Pré-requisitos para telefones de área comum

A primeira coisa a ser feita é confirmar que você já:

- Comprou a licença do Telefone de Área Comum e um Plano de Chamadas.
- Pesquisou e comprou telefones aprovados (veja a lista [aqui](deploying-skype-for-business-online-phones.md)).
- Update the firmware on your phones (See supported firmware [in this topic](getting-phones-for-skype-for-business-online.md)).  You can check the firmware on you phone by doing this:
  - **Telefones Polycom VVX**: acesse **configurações** > **Status** > **plataforma** > **aplicativo** > **principal**.
  - **Telefones Yealink**: Ir para **Status** na tela do telefone principal.
  - **Telefones AudioCodes**: vá para o **Menu** > **Status do dispositivo** > **versão de Firmware** na tela de início.
  - **Telefones de edição de telefone do Lync (LPE)**: vá para o **Menu** > **Informações do sistema** , na tela de início.

    Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.

    Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the  [Set-CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet and setting the *EnableDeviceUpdate* parameter to `false`.

## <a name="setting-up-a-common-area-phone"></a>Configuração de um telefone de área comum
Você precisará seguir estas etapas:

### <a name="step-1---buy-the-licenses"></a>Etapa 1 - Compre as licenças
1. No centro de administração do Office 365, acesse **Faturamento** > **Serviços de compra** e adicione **Outros planos**.

    ![CAP-license.png](../../images/cap-license.png)
2. Clique em **Telefone de Área Comum** > **Comprar agora** > na página **Finalizar compra** clique em **Comprar agora**.
3. Click on to expand **Add-on subscriptions** and then click on to buy a Calling Plan. Choose either the **Domestic Calling Plan** or **Domestic and International Calling Plan**.

> [!Note]
> You don't need a Phone System license. It's included with the **Common Area Phone** license.

Para mais informações sobre licenças, veja [Licenciamento de complementos do Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>Etapa 2 - Criar uma nova conta de usuário para o telefone e atribuir as licenças
1. No centro de administração do Office 365, acesse **Usuários** > **Usuários Ativos** > **Adicionar um usuário**.
2. Coloque um **Nome de usuário** como "Principal" para o primeiro nome e "Recepção" para o segundo nome.
3. Coloque um **Nome para exibição** se "Recepção Principal"não for gerado automaticamente.
4. Coloque um **Nome de usuário** como "RecepçãoPrincipal" ou "LobbyPrincipal".
5. For common area phones, you might want to set a password manually or have the same password for all of you common area phones. Also, you might think about unselecting **Make this user change their password when they first sign in**.

    > [!Tip]
    > WAIT!! Don't click **Add**!! Ugh, if you did click **Add** the do this: Office 365 admin center > **Users** > **Active users** and then find the user. Then on the user's properties page, click **Product licenses** and then click **Edit**. On the **Product licenses** page, turn on **Common Area Phone** and pick either a **Domestic Calling Plan** or a Domestic and **International Calling Plan**.

6. If you are still there, assign the licenses to this user. On the same page, click to expand **Product licenses**. Turn on the following:
   - Telefone de Área Comum
   - Você precisa escolher um **Plano de Chamadas Domésticas** ou um **Plano de Chamadas Domésticas e Internacionais**.

     A atribuição das licenças ficará assim:

     ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

     > [!Note]
     > Só para você saber, o Skype for Business Plan 2 está incluído na licença do **Telefone de Área Comum**.

Para mais detalhes, veja [Adicionar um usuário](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="step-3---assign-a-phone-number-to-the-common-area-phone-user-account"></a>Etapa 3 - Atribuir um número de telefone à conta de usuário do Telefone de Área Comum

![sfb-logo-30x30.png](../../images/sfb-logo-30x30.png)  Atribua um número de telefone ao usuário usando o ** Centro de administração do Skype for Business**

1. No Centro de administração do Office 365 > **Admin centrais** > **Skype para negócios**.
2. No **Centro de administração do Skype for Business** >  **Voz** > **Números de telefone**.
3. Selecione um número na lista de números de telefone e clique em **Atribuir**.
4. Na página **Atribuir**, na caixa **Usuário de voz** digite o nome do usuário usado para o telefone e, em seguida, selecione o usuário no menu suspenso **Selecionar um usuário de voz**.
5. While you're there you will need to add an emergency address. Once you search, look under the **Select emergency address** to pick the right one for you.
6. Clique em **Salvar** e seu usuário ficará assim:

    ![cap-user-number.png](../../images/cap-user-number.png)

   > [!Note]
   > Users will only show up if they have a **Phone System** licence applied. If you just did this, then sometimes it takes a bit for the user to show up in the list.

Para mais detalhes, veja [Obtenção de números de telefone para seus usuários](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md).

If you're wondering, you can also take your phone number that you have with another carrier and "*port*" or transfer them over to Office 365. See, [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).

### <a name="step-4---setting-up-your-phone"></a>Etapa 4 - Configurar seu telefone

**Configuração do modo em um telefone**

The phone or phones you have must have the **Common Area Phone mode** turned on. You might want to check on that to make sure they do.

**Veja um exemplo de como configurar um telefone Polycom VVX**

- Habilite o modo Telefone de Área Comum para o Polycom VVX seguindo estas etapas:
    1. No seu navegador, conecte-se à interface da Web para habilitar o modo CAP.
    2. Depois acesse **Configuração** e na opção **Configuração do Skype for Business**, selecione **Telefone de Área Comum**.
    3. Clique em **Sim** para salvar suas configurações.

- Now that CAP mode is enabled, set up the phone using the phone's display. The display should show **CaAP is enabled**. Then do the following:

    1. Clique em **Configurações**.
    2. Selecione **Avançado**.
    3. Insira a senha.
    4. Em **Configurações de administração**, selecione **Configurações do Telefone de Área Comum**.
    5. Habilite o **CAP** e o **Modo de Administração do CAP**.
    6. Clique em **Salvar configurações**.

- Agora seu telefone está pronto para que você possa entrar na tela inicial.

    1. Entre selecionando **Configurações** > **Recursos** > **Skype for Business.**
    2. Selecione **Credenciais do usuário**e depois **Entrada na Web (CAP)** para gerar um código.
    3. Acesse o [portal de configuração](https://aka.ms/skypecap) e entre como **administrador**.
    4. Insira o nome de exibição (p. ex., Recepção Principal).

       > [!Note]
       > Se a caixa de seleção **Pesquisar apenas Telefones de Área Comum** estiver marcada, desmarque e pesquise novamente.

    5. Na janela de código de pareamento, insira o código exibido no telefone e clique em **Provisão**.

        Após essa última etapa, é possível entrar automaticamente.


> [!NOTE]
> The CAP provisioning site states it will reset the CAP account's password to a random password. Take note that the account the CAP is referring is the Azure Active Directory (AAD) account. If you created the account in AAD only then the process is straightforward. If you have synced an on premises Active Directory to AAD make sure to take note of the credentials you are using that will be changed by CAP provisioning.


### <a name="related-topics"></a>Tópicos relacionados

- Saiba mais sobre os telefones disponíveis em [Implantação de telefones do Skype for Business Online](deploying-skype-for-business-online-phones.md).
- [Obtendo telefones para o Skype for Business Online](getting-phones-for-skype-for-business-online.md)


