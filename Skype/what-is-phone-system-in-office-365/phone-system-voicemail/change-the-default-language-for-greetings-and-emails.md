---
title: "Alterar o idioma padrão para saudações e emails"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 820c3892-1b7e-47d3-ae8d-6e27e7cbcf38
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Phone System
description: 'Learn how to setup Skype for Busineses to use another language for your organization''s default voicemail greeting. '
ms.openlocfilehash: cfbdcfec46a79c6fcef2aff970a05837460f6e72
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-default-language-for-greetings-and-emails"></a><span data-ttu-id="d5266-103">Alterar o idioma padrão para saudações e emails</span><span class="sxs-lookup"><span data-stu-id="d5266-103">Change the default language for greetings and emails</span></span>

<span data-ttu-id="d5266-104">Se você é um [administrador global do Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), você pode configurar Skype for Business executar sua caixa postal de padrão de saudação em outro idioma.</span><span class="sxs-lookup"><span data-stu-id="d5266-104">If you are an [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d), you can set up Skype for Business to play its default voicemail greeting in another language.</span></span> <span data-ttu-id="d5266-105">A saudação de sistema padrão é parecido com "deixar uma mensagem de John Smith.</span><span class="sxs-lookup"><span data-stu-id="d5266-105">The default system greeting is something like, "Please leave a message for John Smith.</span></span> <span data-ttu-id="d5266-106">Após o tom, registre o sua mensagem.</span><span class="sxs-lookup"><span data-stu-id="d5266-106">After the tone, please record your message.</span></span> <span data-ttu-id="d5266-107">Quando terminar a gravação, desligar, ou pressione a tecla de cerquilha para obter mais opções."</span><span class="sxs-lookup"><span data-stu-id="d5266-107">When you finish recording, hang up, or press the pound key for more options."</span></span> 
  
 <span data-ttu-id="d5266-108">**Primeiro, leia estas informações importantes:**</span><span class="sxs-lookup"><span data-stu-id="d5266-108">**First, read this important info:**</span></span>
  
- <span data-ttu-id="d5266-109">**Os idiomas que estão disponíveis para você são determinados pelo local da sua organização**.</span><span class="sxs-lookup"><span data-stu-id="d5266-109">**The languages that are available to you are determined by the location of your organization**.</span></span> <span data-ttu-id="d5266-110">Por exemplo, se sua organização estiver localizada nos Estados Unidos, você pode definir o idioma padrão para inglês ou espanhol.</span><span class="sxs-lookup"><span data-stu-id="d5266-110">For example, if your organization is located in the United States, you can set the default language to English or Spanish.</span></span> <span data-ttu-id="d5266-111">Se sua organização está localizada no Canadá, você pode escolher entre o inglês e francês.</span><span class="sxs-lookup"><span data-stu-id="d5266-111">If your organization is located in Canada, you can choose between English and French.</span></span> <span data-ttu-id="d5266-112">Para obter uma lista dos idiomas com suporte, consulte [idiomas para saudações de caixa postal e mensagens do Skype para negócios](languages-for-voicemail-greetings-and-messages.md).</span><span class="sxs-lookup"><span data-stu-id="d5266-112">For a list of supported languages, see [Languages for voicemail greetings and messages from Skype for Business](languages-for-voicemail-greetings-and-messages.md).</span></span>
    
- <span data-ttu-id="d5266-p103">**Não é possível alterar o idioma do sistema apenas para uma pessoa de sua organização.** Somente o idioma da saudação poderá ser alterado para todas as pessoas na organização.</span><span class="sxs-lookup"><span data-stu-id="d5266-p103">**There's no way to change the system language for only one person in your organization.** You can only change the greeting language for everyone on your organization.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d5266-115">Os usuários podem alterar suas próprias saudação idioma através das suas configurações depois que ele faz logon no.</span><span class="sxs-lookup"><span data-stu-id="d5266-115">Users can change their own greeting language through their settings after they sign in.</span></span> 
  
- <span data-ttu-id="d5266-116">**Você deseja registrar sua mensagem de correio de voz de saída?**</span><span class="sxs-lookup"><span data-stu-id="d5266-116">**Do you want to record your outgoing voicemail message?**</span></span> <span data-ttu-id="d5266-117">Consulte [Verificar Skype para caixa postal de negócios e opções](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span><span class="sxs-lookup"><span data-stu-id="d5266-117">See [Check Skype for Business voicemail and options](https://support.office.com/en-us/article/2deea7f8-831f-4e85-a0d4-b34da55945a8).</span></span>
    
## <a name="change-the-system-language-for-everyone-in-your-organization"></a><span data-ttu-id="d5266-118">Alterar o idioma do sistema para todas as pessoas na organização</span><span class="sxs-lookup"><span data-stu-id="d5266-118">Change the system language for everyone in your organization</span></span>

1. <span data-ttu-id="d5266-119">Entrar com sua conta de [administrador global do Office 365](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) em[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="d5266-119">Sign in with your [Office 365 global administrator](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) account at[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span> 
    
2. <span data-ttu-id="d5266-120">No Centro de administração, escolha **configurações** > **perfil da organização**.</span><span class="sxs-lookup"><span data-stu-id="d5266-120">In the admin center, choose **Settings** > **Organization profile**.</span></span> 
    
     ![Choose Settings and then choose Organization profile.](../../images/9d9de520-bb84-409f-9417-96bd8ec86c48.png)
  
3. <span data-ttu-id="d5266-122">Escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d5266-122">Choose **Edit**.</span></span>
    
    ![Choose Edit.](../../images/e4a0b09d-2b68-4bc8-a0d3-230939843ee2.png)
  
4. <span data-ttu-id="d5266-124">Selecione um idioma na lista **idioma preferencial** para todos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d5266-124">Select a language from the **Preferred language** list for everyone in your organization.</span></span>
    
5. <span data-ttu-id="d5266-125">Escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d5266-125">Choose **Save**.</span></span>
    
## <a name="related-articles-for-the-admin"></a><span data-ttu-id="d5266-126">Artigos relacionados para o administrador</span><span class="sxs-lookup"><span data-stu-id="d5266-126">Related articles for the admin</span></span>

- [<span data-ttu-id="d5266-127">Cite chamar planos no Office 365.</span><span class="sxs-lookup"><span data-stu-id="d5266-127">What are Calling Plans in Office 365?</span></span>](../../what-are-calling-plans-in-office-365/what-are-calling-plans-in-office-365.md)
    
- [<span data-ttu-id="d5266-128">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="d5266-128">Set up Calling Plans</span></span>](../../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
    
- [<span data-ttu-id="d5266-129">Planejar o sistema telefônico no Office 365 com conectividade PSTN local no Skype Business Server 2015 ou o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5266-129">Plan Phone System in Office 365 with on-premises PSTN connectivity in Skype for Business Server 2015 or Lync Server 2013</span></span>](https://go.microsoft.com/fwlink/?LinkId=717947)
    
## <a name="related-topics"></a><span data-ttu-id="d5266-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d5266-130">Related topics</span></span>

- [<span data-ttu-id="d5266-131">Alterar seu idioma de exibição e fuso horário no Office 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="d5266-131">Change your display language and time zone in Office 365 for Business</span></span>](https://support.office.com/en-us/article/Change-your-display-language-and-time-zone-in-Office-365-for-Business-6f238bff-5252-441e-b32b-655d5d85d15b)
    
- <span data-ttu-id="d5266-132">[Adicionar um idioma ou definir as preferências de idioma no Office 2010 e posterior](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span><span class="sxs-lookup"><span data-stu-id="d5266-132">[Add a language or set language preferences in Office 2010 and later](https://support.office.com/en-us/article/Add-a-language-or-set-language-preferences-in-Office-663d9d94-ca99-4a0d-973e-7c4a6b8a827d))</span></span>
    
- [<span data-ttu-id="d5266-133">Habilitar ou alterar o idioma de layout do teclado</span><span class="sxs-lookup"><span data-stu-id="d5266-133">Enable or change a keyboard layout language</span></span>](https://support.office.com/en-us/article/Enable-or-change-a-keyboard-layout-language-1c2242c0-fe15-4bc3-99bc-535de6f4f258)
    

