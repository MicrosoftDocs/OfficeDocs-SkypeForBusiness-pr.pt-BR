---
title: Configuração do Sistema de Telefonia na sua organização
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba como configurar o sistema telefônico (nuvem PBX) para sua organização. '
ms.openlocfilehash: aae5a8e5fc8a0cd2cb20a2e3964c14a89039ce1e
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374446"
---
# <a name="setting-up-phone-system-in-your-organization"></a>Configuração do Sistema de Telefonia na sua organização

The following is a step-by-step guide for setting up Phone System in Office 365. Links to additional, detailed information are available at the end of each step.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Etapa 1: Certifique-se de que o Sistema de Telefonia está disponível em seu país ou região

1.  Primeiro, acesse [Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e selecione seu país ou região na lista na parte superior da página. 
2.  Em **Sistema de Telefonia**, examine a lista de recursos e detalhes. 
3.  Se o Sistema de Telefonia estiver disponível, vá para a etapa 2. 

**Para saber mais sobre disponibilidade regional do Sistema de Telefonia e Audioconferência, consulte [Disponibilidade de Audioconferência e Planos de Chamada por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).**

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Etapa 2: Comprar e atribuir licenças do Sistema de Telefonia e Planos de Chamadas

To assign a Phone System and Calling Plan license to a single user the steps are the same as assigning an Office 365 license. See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses). If you want to assign multiple users in bulk, see [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Etapa 3: Obtenha números de telefone para seus usuários

Antes de você pode configurar os usuários em sua organização façam e recebam chamadas telefônicas, você deve obter números de telefone para eles.

Há três maneiras de obtenção de números para seus usuários:
- Obtenha novos números por meio do centro de administração do Skype for Business.
- Obtenha novos números que não estão disponíveis no centro de administração do Skype for Business.
- Porta ou transferir seus números de existentes do seu provedor de serviço atual ou a operadora de telefone para o Office 365.

You must use the **Add new user numbers** page to see, search, acquire, and reserve those numbers. You can search by Country/Region, State, and City, and then enter the number of phone numbers you will need for your users.

### <a name="get-new-user-phone-numbers"></a>Obtenha números de telefone do novo usuário 
 
![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No painel de navegação esquerdo, acesse **Voz** > **Números de telefone**, clique em **Adicionar novo número** ![Adicionar botão](media/c224fbd0-f0f5-46ce-a1a7-73adf4540ef7.png) e depois clique em **Novos números de usuários**.
    
### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtenha novos números que não estão disponíveis no centro de administração do Skype for Business
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new user numbers.   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Fazer a portabilidade ou transferir os números de telefone de seu provedor de serviços ou de sua operadora de telefonia
  
- If you need 999 or fewer phone numbers for your users, you can use the **New Local Number Port Order** wizard in the Skype for Business admin center. Follow the steps found in [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) to transfer your phone numbers over to Skype for Business Online.
    
- Se você precisar mais do que 999 números de telefone de porta, consulte [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para enviar uma solicitação de serviço de ordem de porta ou a ordem para obter todos esses números de telefone migrados para o Office 365. 

**Para obter informações detalhadas sobre como obter novos números de telefone ou transferir números existentes, consulte [Gerenciar números de telefone da sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).**

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Etapa 4: Obtenha números de telefone do serviço (audioconferência, filas de chamadas, atendedores automáticos)

In addition to getting phone numbers for your users from Office 365, you can search and acquire toll or toll-free phone numbers for services such as audio conferencing (for conference bridges), auto attendants, and call queues (also called service numbers). Service phone numbers have a higher concurrent calling capacity than user or subscriber phone numbers. For example, a service number can handle 100s of calls simultaneously, whereas a user's phone number can only handle a few calls simultaneously.

### <a name="get-new-service-numbers"></a>Obtenha novos números de serviço

![logotipo-sfb-30x30.png](media/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**


1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. Navegue para o **Centro de administração do Office 365** > **Skype for Business**.

3. No painel de navegação esquerdo, vá para **voz** > **números de telefone** > **Adicionar novo número**e clique em **novos números de serviço**.

    > [!IMPORTANT]
    > Para você ver a opção de **voz** no painel de navegação esquerdo no Skype para centro de administração de negócios, primeiro você deve comprar uma licença de complemento de **Conferência de áudio** , uma licença de complemento de **Sistema telefônico** ou pelo menos uma **licença Enterprise E5**.

### <a name="get-new-numbers-that-arent-available-in-the-skype-for-business-admin-center"></a>Obtenha novos números que não estão disponíveis no centro de administração do Skype for Business
  
Sometimes (depending on your country/region) you won't be able to get your new numbers using the Skype for Business admin center. In this case, you will need to download a form and send it back to us. See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) to learn how to request new numbers. 

### <a name="port-or-transfer-existing-service-numbers"></a>Fazer a portabilidade ou transfira números de serviço existentes

If you want to transfer service numbers from your current service provider or carrier, you need to manually submit a port order to Microsoft. You have to submit separate port orders for each type of service number (toll vs. toll-free) that you will be transferring using a Letter of Authorization (LOA). In the Letter of Authorization (LOA), you must select the correct type of service number. When contacting Microsoft support, please make sure you specify that you are transferring a service number (*and not a user or subscriber number*), or the concurrent calling capacity may not be enough to handle call volumes. If you want to transfer phone numbers or do other things with your phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Etapa 5: Se você quiser configurar Planos de Chamadas

If you have been following the steps above, you have already bought and assigned Phone System and licenses and a Calling Plan (step 2) and acquired phone numbers for your users (step 3), so your calling plan is partially set up. Follow the three procedures below to complete the setup of your Calling Plan.

### <a name="add-emergency-addresses-and-locations-for-your-organization"></a>Adicionar endereços de emergências e locais para sua organização

1. Na página de **voz** , escolha **locais de emergência** > **Adicionar novo endereço**.

2. No painel **Novo endereço**, insira um nome para seu endereço. Em seguida, preencha as caixas restantes.
    
     ![Quando você insere um novo endereça de emergência, o formato do nome da rua pode causar um erro.](media/dc1c5ef3-0554-4fb7-9ab1-5ea3ac9e5eb5.png)
  
    > [!TIP]
    > [!DICA] Para clientes ingleses, se o nome da rua for um número, inclua "st" ou "th" no fim, como mostrado na imagem acima.

3. Escolha **Validar**.

    Se necessário, você será solicitado a fazer correções no endereço.

    > [!CAUTION]
    > Validating a street or civic address involves making sure that it is legitimate and correctly formatted. It is possible that a partially correct emergency address, such as if you mistyped the name of the city, may still pass validation. Even though it's misspelled and passed validation, the combination of the misspelled name of city along with the other correct parts of the address are enough information to route the call to the appropriate emergency dispatch center.

    > [!TIP]
    > [!DICA] Se o endereço precisar ser corrigido para resposta a emergências, uma faixa verde será exibida para informar que o endereço foi atualizado.

4. Depois que o endereço for validado, escolha **Salvar**.

### <a name="assign-phone-numbers-and-emergency-addresses-to-users"></a>Atribuir números de telefone e endereços de emergência aos usuários

> [!TIP]
> [!DICA] Se você adicionar mais pessoas à sua empresa antes de realizar esta etapa, é possível que leve **várias horas** para que elas apareçam na página **Usuários de voz**. Há uma latência.

1. Na página **usuários de voz** , selecione as pessoas que você deseja atribuir um número de telefone e endereço de emergência para.

2. No painel Ação, clique em **Atribuir número**.

3. Na página **Atribuir número** , na lista **Selecione o número a ser atribuído** , selecione o número de telefone para o usuário.

4. Selecione um endereço de emergência, insira o nome da cidade na caixa e escolha **Pesquisar**.

    > [!IMPORTANT]
    > If you are outside the United States, your numbers already have an emergency address, but you can change it now. See [Assign or change an emergency address for a user](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user). 
  
5. Depois de atribuir o número de telefone e o endereço de emergência, clique em **Salvar**.

### <a name="tell-your-users-about-their-new-phone-numbers"></a>Informar os usuários sobre seus números de telefone de novo


Recomendamos o envio de emails ou o uso do método de comunicação preferido da sua empresa para avisar as pessoas sobre os novos números de telefone.

Aqui está como eles podem ver o número de telefone no app seus **Skype para negócios** :

1. Entrar no Skype for Business em sua área de trabalho.
    
2. Escolher **Configurações** > **Ferramentas** > **Opções**. 
    
     ![Para ver seu número de telefone, acesse Configurações > Ferramentas > Opções.](media/20637117-91d7-4a7e-9f06-7abc634a9211.png)
  
3. Em seguida, escolha **Telefones**. 
    
    ![A user can see their assign number in the Skype for Business app by choosing Settings > Tools > Options > Phone.](media/0128d667-2bf8-4165-b703-e9b78a15b63c.png)
 
In **Microsoft Teams**, users can see their phone number by clicking **Calls** in the left navigation. The phone number is shown above the dial pad.

![Um usuário pode ver o número de telefone no Microsoft Teams clicando em Chamadas no painel de navegação à esquerda.](media/teams-phone-number.png)

**Para obter informações mais detalhadas sobre todas as etapas da configuração de um Plano de Chamadas consulte [Configurar Planos de Chamadas](set-up-calling-plans.md).**


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Etapa 6: Se você deseja configurar a Audioconferência

Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation! People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.

You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.
  
Para as perguntas frequentes sobre Audioconferência, consulte [Perguntas comuns sobre Audioconferência](audio-conferencing-common-questions.md).
    
1. If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too. For instructions, see [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).

    Decide on your audio conferencing provider. An audio conferencing provider supplies an audio conferencing bridge. The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings. Decide whether to use Microsoft or a third-party audio conferencing provider:

    > [!NOTE]
    > Usuários do Microsoft Teams não podem usar um provedor de serviços de audioconferência de terceiros.

    - **Microsoft como provedor de serviços de audioconferência**: Se você quer a solução mais simples para audioconferência, escolha a Microsoft como seu provedor de serviços.
    
    - **Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider. To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).
 
2. Assign the audio conferencing provider to people who lead or schedule meetings. See [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

3. Set up meeting invitations. The following steps are optional, but a lot of admins like to do them: 
  
   1. [Personalizar convites de reunião em Skype para negócios](/skypeforbusiness/set-up-skype-for-business-online/customize-meeting-invitations). Os números de discagem definidos para o usuário serão adicionados automaticamente aos convites da reunião enviados aos participantes. No entanto, você pode adicionar seus próprios links de ajuda e informações jurídicas, uma mensagem de texto e um pequeno gráfico da empresa.
    
   2. Defina os números de telefone de conferência de áudio para que estão incluídos na organizadores de reuniões convidam [em Skype para a empresa](/skypeforbusiness/audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites) ou [em equipes da Microsoft](set-the-phone-numbers-included-on-invites-in-teams.md). Esse é o número de telefone que serão exibidas na reunião programada pelo usuário.
    
   3. Definir idiomas de atendedor automático para conferência de áudio [no Skype para a empresa](/skypeforbusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing) ou [em equipes da Microsoft](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) que o atendedor automático de conferência de áudio usa para saudar um chamador quando eles discam para um número de telefone de conferência de áudio. Esta etapa só é válida se você estiver usando o Microsoft como provedor de áudio.
    
   4. Definir o tamanho do PIN para reuniões de conferência de áudio [em Skype para a empresa](/skypeforbusiness/audio-conferencing-in-office-365/set-the-pin-length-for-audio-conferencing-meetings) ou [em equipes da Microsoft](set-the-pin-length-for-audio-conferencing-meetings-in-teams.md).
    
      > [!NOTE]
      > This feature is not yet available to customers using Office 365 operated by 21Vianet in China. To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).

**Para obter mais informações sobre Audioconferência, consulte [Configurar Audioconferências](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing).**

## <a name="step-7-if-you-want-to-set-up-a-phone-system-call-queue"></a>Etapa 7: Se você deseja configurar uma fila de chamadas do Sistema de Telefonia

Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold. You can create single or multiple call queues for your organization.

Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).
  
> [!NOTE]
> If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.

Para criar uma nova fila de chamadas, no **centro de administração do Skype for Business**, clique em **Roteamento de chamadas** > **Filas de chamadas**, depois clique em **Adicionar nova** e siga as instruções da **Etapa 3** do artigo  [Criar uma fila de chamadas para Sistema de Telefonia](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue#step-3---create-a-new-call-queue).

**Para obter mais detalhes sobre as filas de chamada, consulte [Criar uma fila de chamada do Sistema de Telefonia](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).**

## <a name="step-8-if-you-want-to-set-up-a-phone-system-auto-attendant"></a>Etapa 8: Se você quiser configurar um atendedor automático do Sistema de Telefonia

Auto attendants let people that call in to your organization and navigate a menu system to get them to the right department, call queue, person, or the operator. You can create an auto attendant for your organization by using the Skype for Business admin center.

Para criar um novo atendedor automático, no centro de administração do Skype for Business, clique em **Roteamento de chamadas** > **Atendedores automáticos**, depois clique em **Adicionar novo** e siga as instruções para cada página na **Etapa 2** do artigo [Configurar um atendedor automático para Sistema de Telefonia](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant#step-2---create-a-new-auto-attendant).

**Para obter mais detalhes sobre os atendedores automáticos de Sistema de Telefonia, consulte [Configurar um atendedor automático de Sistema de Telefonia](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).**

## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Etapa 9: Atribua números de telefone de serviço (audioconferência, filas de chamadas, atendedores automáticos)

Once you have your service numbers from **Step 4 above**, you need to assign them to each type of service that you want. For example, if you want a dedicated service phone number (toll or toll-free), you will need to assign the number to the conferencing bridge.

- Para Audioconferências, você pode atribuir um número dedicado a uma ponte de Audioconferência acessando o **centro de administração do Office 365** > **Centros de administração** > **Skype for Business** > **Audioconferências** e clicando em ponte de conferência ou visualizando  [Alterar os números pagos ou gratuitos da sua ponte de Audioconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- For Auto Attendants, you can assign a dedicated number to an auto attendant by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Auto attendants** and click on the auto attendant. On the **General** page the service number you already have will be listed in the **Phone number** drop down. For details, see [Set up a Phone System Auto Attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant).

- For Call Queues, you can assign a dedicated number to a call queue by going to **Office 365 admin center** > **Admin centers** > **Skype for Business** > **Call routing** > **Call queues** and click on the call queue. On the **General** page the service number you already have will be listed in the **Phone number** drop down. For details, see [Create a Phone System call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue).

**Para obter informações detalhadas sobre como obter novos números de serviço e fazer a portabilidade de números de serviço existentes, consulte [Obter números de telefone de serviço](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers).**

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Etapa 10: Configurar os créditos de comunicações para sua organização

You will need to set up Communications Credits if you would like to use toll-free numbers with Skype for Business and Microsoft Teams. Also, we recommend that you set up Communications Credits for your Calling Plans (Domestic or International) and Audio Conferencing users who need the ability to dial out to **any destination**. Many countries/regions are included, but some destinations may not be included in your Calling Plan or Audio Conferencing subscriptions. If you don't set up Communications Credits billing and assign a **Communications Credits** license to your users and you run out minutes for your organization (depending on your Calling Plan or Audio Conferencing plan in your country/region), those users won't be able to make calls or dial out from Audio Conferencing meetings. You can get more information, including recommended funding amounts, by reading [What are Communications Credits?](what-are-communications-credits.md)
  
> [!NOTE]
> Para descobrir quanto isso custa, [consulte as taxas aqui](https://go.microsoft.com/fwlink/p/?LinkId=799523 ).

### <a name="to-set-up-communications-credits"></a>Configurar Créditos de Comunicação

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. No painel de navegação à esquerda no centro de administração do Office 365, acesse **Cobrança** > **Assinaturas** > **Complementos** > **Comprar complementos** e escolha **Créditos de Comunicação** > **Comprar agora**.

3. Na página de assinatura **Créditos de Comunicação**, preencha as informações e clique em **Avançar**.

4. Insira suas informações de pagamento e clique em **Fazer pedido**.
    >[!IMPORTANT]
    >If you are a volume licensing customer, you may choose your enterprise agreement number for payment. If you have multiple enterprise agreement numbers, you will be able to select which enterprise agreement you would like to use for payment. You will also be given an opportunity to specify a purchase order number to associate with the enterprise agreement number (if applicable).
    
**Para obter mais informações detalhadas sobre como configurar Créditos de Comunicação, consulte [Configurar créditos de Comunicação para a sua organização](set-up-communications-credits-for-your-organization.md).**
  
### <a name="assign-a-communications-credits-license-to-users"></a>Atribuir uma licença de Créditos de Comunicação aos usuários

1. Entre no Office 365 com sua conta corporativa ou de estudante.

2. No painel de navegação à esquerda do Centro de administração do Office 365, vá para **usuários** > **usuários ativos**e selecione um ou mais usuários da lista.

3. No painel Ação em **Licenças de**, clique em **Editar**.

4. Na página **licenças do produto** , alternar **Créditos de comunicações** para **em** para atribuir essa licença e clique em **Salvar**.

    > [!NOTE]
    > Mesmo se você tiver usuários que receberem uma licença **Enterprise E5** , ainda é recomendado que você faça isso.

**Para saber mais sobre como atribuir licenças Créditos de Comunicação, consulte [Configurar Créditos de Comunicação para sua organização](set-up-communications-credits-for-your-organization.md).**

## <a name="related-topics"></a>Tópicos relacionados
[Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365](here-s-what-you-get-with-phone-system.md)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers)

[Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
