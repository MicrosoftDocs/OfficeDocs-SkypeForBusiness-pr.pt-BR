---
title: Planejamento da Autenticação Moderna (ADAL) com o Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Este artigo explica o que é a Autenticação Moderna (baseada na ADAL (Biblioteca de Autenticação do Active Directory) e no OAuth 2.0.
ms.openlocfilehash: bd5d172fe4589cbd28c5b22507ad8603695ed62f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816221"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="0ea23-103">Como usar a Autenticação Moderna (ADAL) com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0ea23-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="0ea23-104">Este artigo apresenta a Autenticação Moderna (que se baseia na ADAL (Biblioteca de Autenticação do Active Directory) e no OAuth 2.0) que pode ser encontrada na Atualização Cumulativa de março de 2016 do Skype for Business para Skype for Business Server 2015 ou na versão inicial do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0ea23-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="0ea23-105">O que é a ADAL?</span><span class="sxs-lookup"><span data-stu-id="0ea23-105">What is ADAL?</span></span>

<span data-ttu-id="0ea23-106">A ADAL é o acrônimo para a "Biblioteca de Autenticação do Active Directory" e, juntamente com o OAuth 2.0, é um dos princípios da Autenticação Moderna.</span><span class="sxs-lookup"><span data-stu-id="0ea23-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="0ea23-107">Essa biblioteca de códigos foi projetada para disponibilizar recursos seguros em seu diretório para aplicativos cliente (como o Skype for Business) por meio de tokens de segurança.</span><span class="sxs-lookup"><span data-stu-id="0ea23-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="0ea23-108">A ADAL trabalha com o OAuth 2.0 para habilitar mais cenários de autenticação e autorização, como a MFA (Autenticação Multifatória) e mais formas de Autenticação SAML.</span><span class="sxs-lookup"><span data-stu-id="0ea23-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="0ea23-109">Uma variedade de aplicativos que atuam como clientes pode aproveitar a Autenticação Moderna para obter recursos seguros.</span><span class="sxs-lookup"><span data-stu-id="0ea23-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="0ea23-110">No Skype for Business Server, essa tecnologia é usada entre clientes locais e servidores locais para dar aos usuários um nível adequado de autorização aos recursos.</span><span class="sxs-lookup"><span data-stu-id="0ea23-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="0ea23-111">As conversas de Autenticação Moderna (que são baseadas na ADAL e no OAuth 2.0) têm alguns elementos em comum.</span><span class="sxs-lookup"><span data-stu-id="0ea23-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="0ea23-112">Há um cliente fazendo uma solicitação para um recurso, nesse caso, o cliente é o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="0ea23-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="0ea23-113">Há um recurso para o qual o cliente precisa de um nível específico de acesso, e esse recurso é protegido por um serviço de diretório, neste caso o recurso é o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0ea23-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="0ea23-114">Há uma conexão OAuth, em outras palavras, uma conexão dedicada  *a*  autorizar um usuário a acessar um recurso.</span><span class="sxs-lookup"><span data-stu-id="0ea23-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="0ea23-115">(OAuth também é conhecido pelo nome mais descritivo, auth 'Servidor para Servidor' e é frequentemente abreviado como S2S.)</span><span class="sxs-lookup"><span data-stu-id="0ea23-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="0ea23-116">Nas conversas da Autenticação Moderna (ADAL) do Skype for Business Server, o Skype for Business Server se comunica por meio do ADFS (ADFS 3.0 no Windows Server 2012 R2).</span><span class="sxs-lookup"><span data-stu-id="0ea23-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="0ea23-117">A autenticação pode acontecer usando algum outro Provedor de Identidade (IdP), mas o Skype for Business Server precisa ser configurado para se comunicar diretamente com o ADFS.</span><span class="sxs-lookup"><span data-stu-id="0ea23-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="0ea23-118">Se você ainda não configurou o ADFS para funcionar com o Skype for Business Server, conclua [a instalação do ADFS.](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0ea23-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="0ea23-119">A ADAL está incluída na Atualização Cumulativa de março de 2016 para o Skype for Business Server 2015, e a Atualização Cumulativa de março de 2016 para o Skype for **Business** deve ser instalada e é necessária para uma configuração bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="0ea23-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="0ea23-120">Para o Skype for Business Server 2019, ele está disponível na versão inicial do produto.</span><span class="sxs-lookup"><span data-stu-id="0ea23-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0ea23-121">Durante o lançamento inicial, a Autenticação Moderna em um ambiente local só será suportada se não houver topologia mista do Skype envolvida.</span><span class="sxs-lookup"><span data-stu-id="0ea23-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="0ea23-122">Por exemplo, se o ambiente for puramente Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0ea23-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="0ea23-123">Esta instrução pode estar sujeita a alterações.</span><span class="sxs-lookup"><span data-stu-id="0ea23-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="0ea23-124">Um pacote do PowerShell incluindo arquivos .ps1 com os comandos usados pela ADAL deve ser baixado para uma configuração bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="0ea23-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="0ea23-125">Para obter informações sobre como implementar a Autenticação Moderna no Skype for Business, consulte: Como usar a Autenticação Moderna [(ADAL)](../../manage/authentication/use-adal.md) com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0ea23-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
