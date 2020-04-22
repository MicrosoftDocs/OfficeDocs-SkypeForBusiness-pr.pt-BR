---
title: Alterar o idioma padrão de saudações e emails
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Saiba como configurar o Skype for Business para usar outro idioma para a saudação de correio de voz padrão da sua organização.
ms.openlocfilehash: 5cff20da14dac942527b8b667731c24a47f0cf29
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780360"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="f7363-103">Alterar o idioma padrão de saudações e emails</span><span class="sxs-lookup"><span data-stu-id="f7363-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="f7363-104">Se você for um [administrador global](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), poderá configurar o Skype for Business para reproduzir sua saudação de correio de voz padrão em outro idioma.</span><span class="sxs-lookup"><span data-stu-id="f7363-104">If you are a [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="f7363-105">A saudação padrão do sistema é semelhante a: "Por favor, deixe uma mensagem para John Smith.</span><span class="sxs-lookup"><span data-stu-id="f7363-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="f7363-106">Grave sua mensagem após o sinal.</span><span class="sxs-lookup"><span data-stu-id="f7363-106">After the tone, please record your message.</span></span> <span data-ttu-id="f7363-107">Ao final da gravação, desligue ou pressione a tecla jogo da velha para ver mais opções".</span><span class="sxs-lookup"><span data-stu-id="f7363-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="f7363-108">**Primeiro, leia estas informações importantes:**</span><span class="sxs-lookup"><span data-stu-id="f7363-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="f7363-109">**Os idiomas disponíveis são determinados pelo local da organização**.</span><span class="sxs-lookup"><span data-stu-id="f7363-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="f7363-110">Por exemplo, se a sua organização está nos Estados Unidos, você pode definir o idioma padrão como inglês ou espanhol.</span><span class="sxs-lookup"><span data-stu-id="f7363-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="f7363-111">Se a sua organização está no Canadá, você pode escolher entre inglês e francês.</span><span class="sxs-lookup"><span data-stu-id="f7363-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="f7363-112">Para ver a lista de idiomas com suporte, acesse [Idiomas para saudações e mensagens da caixa postal do Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f7363-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="f7363-p103">**Não é possível alterar o idioma do sistema apenas para uma pessoa de sua organização.** Somente o idioma da saudação poderá ser alterado para todas as pessoas na organização.</span><span class="sxs-lookup"><span data-stu-id="f7363-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f7363-115">Depois de entrar, os usuários podem alterar seu próprio idioma de saudação por meio das configurações.</span><span class="sxs-lookup"><span data-stu-id="f7363-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="f7363-116">**Deseja gravar sua mensagem de caixa postal de saída?**</span><span class="sxs-lookup"><span data-stu-id="f7363-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="f7363-117">Veja [Verificar a caixa postal e as opções do Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="f7363-117">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span> <span data-ttu-id="f7363-118">Para o Microsoft Teams-os usuários podem alterar as configurações de caixa postal nas [configurações do cliente de área de trabalho do teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="f7363-118">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>

- <span data-ttu-id="f7363-119">**Deseja alterar o idioma do prompt de correio de voz?**</span><span class="sxs-lookup"><span data-stu-id="f7363-119">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="f7363-120">Para o Skype for Business [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) -e escolha um novo idioma em **idioma do pedido**.</span><span class="sxs-lookup"><span data-stu-id="f7363-120">For Skype for Business -  [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span> <span data-ttu-id="f7363-121">Para o Microsoft Teams-os usuários podem alterar as configurações de caixa postal nas [configurações do cliente de área de trabalho do teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span><span class="sxs-lookup"><span data-stu-id="f7363-121">For Microsoft Teams - Users can change their voicemail settings from the [Teams desktop client settings](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f)</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="f7363-122">Alterar o idioma do sistema para todas as pessoas na organização</span><span class="sxs-lookup"><span data-stu-id="f7363-122">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="f7363-123">Entre com sua conta de [administrador global](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="f7363-123">Sign in with your [global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="f7363-124">No centro de administração do Microsoft 365, **escolha** > **Settings** > configurações configurações**perfil da organização**.</span><span class="sxs-lookup"><span data-stu-id="f7363-124">In the Microsoft 365 admin center, choose **Settings** > **Settings** > **Organization profile**.</span></span> 
    
     ![Captura de tela mostrando a escolha de configurações e o perfil da organização.](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="f7363-126">Escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f7363-126">Choose **Edit**.</span></span>
    
    ![Captura de tela mostrando a opção de edição.](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="f7363-128">Selecione um idioma na lista **Idioma preferencial** para todas as pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f7363-128">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="f7363-129">Escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f7363-129">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="f7363-130">Artigos relacionados para o administrador</span><span class="sxs-lookup"><span data-stu-id="f7363-130">Related articles for the admin</span></span>

- [<span data-ttu-id="f7363-131">Sistema de Telefonia e Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="f7363-131">Phone System and Calling Plans</span></span>](calling-plan-landing-page.md)
    
- [<span data-ttu-id="f7363-132">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="f7363-132">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="f7363-133">Planejar o sistema telefônico no Office 365 com conectividade PSTN local no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f7363-133">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="f7363-134">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f7363-134">Related topics</span></span>

- [<span data-ttu-id="f7363-135">Alterar seu idioma de exibição e fuso horário no Office 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="f7363-135">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="f7363-136">[Adicionar um idioma ou definir preferências de idioma no Office 2010 e posterior](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="f7363-136">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="f7363-137">Habilitar ou alterar o idioma de layout do teclado</span><span class="sxs-lookup"><span data-stu-id="f7363-137">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
