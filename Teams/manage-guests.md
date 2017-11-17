---
title: Gerenciamento do acesso de convidados no Microsoft Teams
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: 
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: beb9e46248569d46e1deb6d9210fde4ba329faaf
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2017
---
<a name="manage-guest-access-to-microsoft-teams"></a><span data-ttu-id="2c949-102">Gerenciamento do acesso de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2c949-102">Manage guest access to Microsoft Teams</span></span>
======================================

<span data-ttu-id="2c949-103">O acesso de convidados está incluído em todas as inscrições do Office 365 Business Premium, Office 365 Enterprise e Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="2c949-103">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="2c949-104">Não é necessária nenhuma licença adicional do Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c949-104">No additional Office 365 license is necessary.</span></span>
  
    
    
<span data-ttu-id="2c949-105">O acesso de convidados no Teams é uma configuração em nível de locatário e está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="2c949-105">Teams guest access is a tenant-level setting and is turned off by default.</span></span> <span data-ttu-id="2c949-106">Os administradores de TI podem adicionar convidados em nível de locatário, definir e gerenciar políticas e permissões de usuários convidados, determinar quais usuários podem convidar convidados e extrair relatórios sobre a atividade do usuário convidado.</span><span class="sxs-lookup"><span data-stu-id="2c949-106">IT admins can add guests at the tenant level, set and manage guest user policies and permissions, determine which users can invite guests, and pull reports on guest user activity.</span></span> <span data-ttu-id="2c949-107">Esses controles estão disponíveis no centro de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c949-107">These controls are available through the Office 365 admin center.</span></span> <span data-ttu-id="2c949-108">O conteúdo e as atividades dos usuários convidados estão sob a mesma proteção de conformidade e auditoria que o restante do Office 365.</span><span class="sxs-lookup"><span data-stu-id="2c949-108">Guest user content and activities are under the same compliance and auditing protection as the rest of Office 365.</span></span>
  
    
    

> [!NOTE]
> <span data-ttu-id="2c949-109">A configuração de locatário do acesso ao Teams impede o acesso do convidado.</span><span class="sxs-lookup"><span data-stu-id="2c949-109">The Teams guest access tenant setting only prevents guest sign-in.</span></span> <span data-ttu-id="2c949-110">Os proprietários de equipe poderão convidar novos convidados e adicionar usuários convidados do diretório existente a suas respectivas equipes.</span><span class="sxs-lookup"><span data-stu-id="2c949-110">Team owners will be able to invite new guests and add existing directory guest users to their respective teams.</span></span> <span data-ttu-id="2c949-111">Como lembrete, o Teams sempre obedece as configurações externas do Azure Active Directory para permitir ou impedir a adição de usuários convidados ao locatário.</span><span class="sxs-lookup"><span data-stu-id="2c949-111">As a reminder, Teams always honors Azure Active Directory external settings to allow or prevent guest user addition to the tenant.</span></span> 
  
    
    

<span data-ttu-id="2c949-112">Além disso, você pode usar o portal do Azure Active Directory para gerenciar os convidados e o seu acesso aos recursos do Office 365 e do Teams.</span><span class="sxs-lookup"><span data-stu-id="2c949-112">In addition, you can use the Azure Active Directory portal to manage guests and their access to Office 365 and Teams resources.</span></span> <span data-ttu-id="2c949-113">O acesso de convidados das equipes faz uso dos recursos de colaboração entre empresas (B2B) do Azure Active Directory como a infraestrutura subjacente para armazenar informações de princípios de segurança, como propriedades de identidade, assinaturas e configurações de autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="2c949-113">Teams guest access makes use of Azure Active Directory business-to-business (B2B) collaboration capabilities as the underlying infrastructure to store security principles information such as identity properties, memberships, and multi-factor authentication settings.</span></span> <span data-ttu-id="2c949-114">Para saber mais sobre o Azure Active Directory B2B, consulte [O que é a colaboração do Azure AD B2B?](https://go.microsoft.com/fwlink/p/?linkid=853011) e [Perguntas frequentes de colaboração do Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=853020).</span><span class="sxs-lookup"><span data-stu-id="2c949-114">To learn more about Azure Active Directory B2B, see [What is Azure AD B2B collaboration?](https://go.microsoft.com/fwlink/p/?linkid=853011) and [Azure Active Directory B2B collaboration FAQs](https://go.microsoft.com/fwlink/p/?linkid=853020).</span></span>
  