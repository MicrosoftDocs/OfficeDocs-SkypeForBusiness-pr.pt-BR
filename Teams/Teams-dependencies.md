---
title: "Dependências do Office 365 para o Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: O Microsoft Teams depende dos grupos do Office 365, do SharePoint Online e do OneDrive for Business.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e04770535976f509a8ac16cf054ea5e6760b5231
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2017
---
<a name="office-365-dependencies-for-microsoft-teams"></a><span data-ttu-id="a92b2-103">Dependências do Office 365 para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a92b2-103">Office 365 licensing for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="a92b2-104">O Microsoft Teams depende dos grupos do Office 365 para armazenar assinaturas equipes e outras propriedades, como configurações de classificação de dados da equipe.</span><span class="sxs-lookup"><span data-stu-id="a92b2-104">In addition, Teams relies on Office 365 groups to store teams' memberships and other properties such as team data classification settings.</span></span> <span data-ttu-id="a92b2-105">Os grupos do Office 365 são um serviço que oferece assinatura cruzada de aplicativos para um conjunto de ativos compartilhados de equipe, como um site do SharePoint ou um painel de controle do Power BI, para que a equipe possa colaborar de forma eficaz e segura.</span><span class="sxs-lookup"><span data-stu-id="a92b2-105">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

<span data-ttu-id="a92b2-106">O Teams também depende do SharePoint Online e do OneDrive for Business para armazenar arquivos e documentos para canais e conversas de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="a92b2-106">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span> <span data-ttu-id="a92b2-107">Além disso, o Teams depende dos grupos do Office 365 para armazenar assinaturas equipes e outras propriedades, como configurações de classificação de dados da equipe.</span><span class="sxs-lookup"><span data-stu-id="a92b2-107">In addition, Teams relies on Office 365 groups to store teams' memberships and other properties such as team data classification settings.</span></span> <span data-ttu-id="a92b2-108">Os convidados estão sujeitos aos limites de serviço do [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e do [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="a92b2-108">Yes, guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>
  
    
    
<span data-ttu-id="a92b2-109">Para habilitar a experiência completa de acesso de convidados no Teams, os administradores do Office 365 precisam selecionar **Habilitar** nas seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a92b2-109">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="a92b2-110">No SharePoint Online: **Permitir apenas compartilhamento com usuários externos já constantes do diretório**</span><span class="sxs-lookup"><span data-stu-id="a92b2-110">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="a92b2-111">Para obter mais informações, consulte [Gerenciar compartilhamento externo para o seu ambiente do SharePoint Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span><span class="sxs-lookup"><span data-stu-id="a92b2-111">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="a92b2-112">Nos grupos do Office 365: **Permitir que proprietários de grupos adicionem aos grupos pessoas externas à organização**</span><span class="sxs-lookup"><span data-stu-id="a92b2-112">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="a92b2-113">Para obter mais informações, consulte [Controle do acesso de convidados no Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="a92b2-113">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="a92b2-114">Você pode gerenciar as configurações de usuário externo do SharePoint Online para o site de equipe conectado ao Teams.</span><span class="sxs-lookup"><span data-stu-id="a92b2-114">Yes, you can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="a92b2-115">Para obter mais detalhes, veja [Gerenciar as configurações do site da sua equipe do SharePoint](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span><span class="sxs-lookup"><span data-stu-id="a92b2-115">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>