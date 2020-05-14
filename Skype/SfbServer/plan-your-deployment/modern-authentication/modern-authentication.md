---
title: Planejar a autenticação moderna no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Planejamento de tópicos para autenticação e autorização para o Skype for Business Server, incluindo a integração com outros produtos
ms.openlocfilehash: 3b673a9f88895ac57277ef51b51fe0a4a27c64a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221575"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="8ad9a-103">Discutir a autenticação e a autorização no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8ad9a-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="8ad9a-104">A autenticação e a autorização são conceitos relacionados, mas não funcionam diferentes para você (embora ambos sejam necessários).</span><span class="sxs-lookup"><span data-stu-id="8ad9a-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="8ad9a-105">Resumir os termos simples, Authenciation (Authn) depende dos segredos apenas de um usuário válido conhece ou tem e que pode ser uma senha, código, impressão digital, certificado, uma combinação de declarações sobre o usuário que é verdadeira ou uma combinação dessas coisas usadas em conjunto.</span><span class="sxs-lookup"><span data-stu-id="8ad9a-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="8ad9a-106">Authn é um processo para provar que você é quem diz ser.</span><span class="sxs-lookup"><span data-stu-id="8ad9a-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="8ad9a-107">Autorização (AuthZ) é preocupado com o que você tem acesso depois de comprovar quem é você.</span><span class="sxs-lookup"><span data-stu-id="8ad9a-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="8ad9a-108">Ele determina o que você tem permissão para ver, editar e acessar o caso.</span><span class="sxs-lookup"><span data-stu-id="8ad9a-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="8ad9a-109">Por exemplo, você pode ter um poderoso acesso de administrador do conjunto de sites ao SharePoint Online, mas se você alternar para outra carga de trabalho online, como o Skype for Business Online, você pode ter os privilégios para solucionar problemas de usuário, não alterar a configuração do servidor ou servidores.</span><span class="sxs-lookup"><span data-stu-id="8ad9a-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="8ad9a-110">Em uma terceira carga de trabalho, como o Exchange Online, você pode ter apenas o acesso do usuário médio.</span><span class="sxs-lookup"><span data-stu-id="8ad9a-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="8ad9a-111">A AuthZ verifica o que é e quanto acesso você tem a serviços/worloads, aplicativos, arquivos e outros dados.</span><span class="sxs-lookup"><span data-stu-id="8ad9a-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="8ad9a-112">Nossos exemplos envolvem Propriedades online, como o SharePoint e o Exchange Online, mas os processos de Authn e AuthZ trabalham no local e em um local híbrido da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="8ad9a-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="8ad9a-113">Em última análise, as ferramentas como o AAD Connect e o ADFS se envolvem na autenticação de contas e senhas locais no AD da nuvem (que é o AD do Azure) ou invasos no fluxo de AuthZ para que um usuário não tenha suas credenciais freqüentemente solicitadas, digamos ao alternar entre cargas de trabalho na nuvem, criando cenários de logon único.</span><span class="sxs-lookup"><span data-stu-id="8ad9a-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="8ad9a-114">Mas eles não são, sozinhos, Authn ou AuthZ, apenas parte da mecânica.</span><span class="sxs-lookup"><span data-stu-id="8ad9a-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="8ad9a-115">Hoje, muitas tecnologias consideram esses processos (Authn e AuthZ) como um mecanismo, e você ouvirá muitas referências a processos de autenticação que também incluem autorização neles.</span><span class="sxs-lookup"><span data-stu-id="8ad9a-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="8ad9a-116">É importante lembrar que a primeira etapa no acesso do usuário é Authn, provando que você é quem diz ser e que a AuthZ usa o conhecimento de quem o usuário deve determinar o que ele ou ela tem que acessar (como você verá com autorização aberta ou OAuth).</span><span class="sxs-lookup"><span data-stu-id="8ad9a-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="8ad9a-117">Tópicos de planejamento de autenticação e autorização</span><span class="sxs-lookup"><span data-stu-id="8ad9a-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="8ad9a-118">Como usar a ADAL (autenticação moderna) com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8ad9a-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="8ad9a-119">Topologias do Skype for Business compatíveis com a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="8ad9a-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="8ad9a-120">Planejar a desativação de métodos de autenticação herdados interna e externamente em sua rede.</span><span class="sxs-lookup"><span data-stu-id="8ad9a-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

