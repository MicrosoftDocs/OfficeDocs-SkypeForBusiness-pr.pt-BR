---
title: Alterar o idioma padrão de saudações e emails
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
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
description: 'Saiba como configurar o Skype for Business para usar outro idioma na saudação da mensagem de voz padrão de sua organização. '
ms.openlocfilehash: aeebc9907e0f2933921e449a7915bd8cced9cd66
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678350"
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="786be-103">Alterar o idioma padrão de saudações e emails</span><span class="sxs-lookup"><span data-stu-id="786be-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="786be-104">Se você é [Administrador global do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), pode configurar o Skype for Business para reproduzir a saudação padrão da caixa postal em outro idioma.</span><span class="sxs-lookup"><span data-stu-id="786be-104">If you are an [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="786be-105">A saudação padrão do sistema é semelhante a: "Por favor, deixe uma mensagem para John Smith.</span><span class="sxs-lookup"><span data-stu-id="786be-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="786be-106">Grave sua mensagem após o sinal.</span><span class="sxs-lookup"><span data-stu-id="786be-106">After the tone, please record your message.</span></span> <span data-ttu-id="786be-107">Ao final da gravação, desligue ou pressione a tecla jogo da velha para ver mais opções".</span><span class="sxs-lookup"><span data-stu-id="786be-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="786be-108">**Primeiro, leia estas informações importantes:**</span><span class="sxs-lookup"><span data-stu-id="786be-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="786be-109">**Os idiomas disponíveis são determinados pelo local da organização**.</span><span class="sxs-lookup"><span data-stu-id="786be-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="786be-110">Por exemplo, se a sua organização está nos Estados Unidos, você pode definir o idioma padrão como inglês ou espanhol.</span><span class="sxs-lookup"><span data-stu-id="786be-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="786be-111">Se a sua organização está no Canadá, você pode escolher entre inglês e francês.</span><span class="sxs-lookup"><span data-stu-id="786be-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="786be-112">Para ver a lista de idiomas com suporte, acesse [Idiomas para saudações e mensagens da caixa postal do Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="786be-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="786be-p103">**Não é possível alterar o idioma do sistema apenas para uma pessoa de sua organização.** Somente o idioma da saudação poderá ser alterado para todas as pessoas na organização.</span><span class="sxs-lookup"><span data-stu-id="786be-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="786be-115">Depois de entrar, os usuários podem alterar seu próprio idioma de saudação por meio das configurações.</span><span class="sxs-lookup"><span data-stu-id="786be-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="786be-116">**Deseja gravar sua mensagem de caixa postal de saída?**</span><span class="sxs-lookup"><span data-stu-id="786be-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="786be-117">Veja [Verificar a caixa postal e as opções do Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="786be-117">See [Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>

- <span data-ttu-id="786be-118">**Você deseja alterar o idioma de prompt de caixa postal?**</span><span class="sxs-lookup"><span data-stu-id="786be-118">**Do you want to change the voicemail prompt language?**</span></span> <span data-ttu-id="786be-119">Vá para [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) e escolha um novo idioma em **Prompt de idioma**.</span><span class="sxs-lookup"><span data-stu-id="786be-119">Go to [https://mysettings.lync.com/voicemail](https://mysettings.lync.com/voicemail) and choose a new language under **Prompt Language**.</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="786be-120">Alterar o idioma do sistema para todas as pessoas na organização</span><span class="sxs-lookup"><span data-stu-id="786be-120">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="786be-121">Entrar com sua conta de [administrador global do Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) em[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="786be-121">Sign in with your [Office 365 global administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="786be-122">No Centro de administração do Office 365, escolha **configurações** > **perfil da organização**.</span><span class="sxs-lookup"><span data-stu-id="786be-122">In the Office 365 admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Choose Settings and then choose Organization profile.](media/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="786be-124">Escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="786be-124">Choose **Edit**.</span></span>
    
    ![Escolha Editar.](media/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="786be-126">Selecione um idioma na lista **Idioma preferencial** para todas as pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="786be-126">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="786be-127">Escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="786be-127">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="786be-128">Artigos relacionados para o administrador</span><span class="sxs-lookup"><span data-stu-id="786be-128">Related articles for the admin</span></span>

- [<span data-ttu-id="786be-129">O que são Planos de Chamadas no Office 365?</span><span class="sxs-lookup"><span data-stu-id="786be-129">What are Calling Plans in Office 365?</span></span>](what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="786be-130">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="786be-130">Set up Calling Plans</span></span>](set-up-calling-plans.md)
    
- [<span data-ttu-id="786be-131">Planejar o sistema telefônico no Office 365 com conectividade PSTN local no Skype Business Server</span><span class="sxs-lookup"><span data-stu-id="786be-131">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="786be-132">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="786be-132">Related topics</span></span>

- [<span data-ttu-id="786be-133">Alterar seu idioma de exibição e fuso horário no Office 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="786be-133">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="786be-134">[Adicionar um idioma ou definir preferências de idioma no Office 2010 e posterior](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d)</span><span class="sxs-lookup"><span data-stu-id="786be-134">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="786be-135">Habilitar ou alterar o idioma de layout do teclado</span><span class="sxs-lookup"><span data-stu-id="786be-135">Enable or change a keyboard layout language</span></span>](https://support.office.com/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    
  
 
