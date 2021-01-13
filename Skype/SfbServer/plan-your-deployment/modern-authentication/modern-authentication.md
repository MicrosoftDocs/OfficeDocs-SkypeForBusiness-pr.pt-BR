---
title: Planejar a autenticação moderna no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: Tópicos de planejamento para autenticação e autorização para o Skype for Business Server, incluindo integração com outros produtos
ms.openlocfilehash: c657a2b3609c5fb93f7f915c460cd3334f7fac03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816241"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="6d706-103">Discutir autenticação e autorização no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6d706-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="6d706-104">Autenticação e autorização são conceitos relacionados, mas fazem um trabalho diferente para você (embora ambos sejam necessários).</span><span class="sxs-lookup"><span data-stu-id="6d706-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="6d706-105">Em termos simples, a authenciação (AuthN) depende de segredos que apenas um usuário válido conhece ou tem, e isso pode ser uma senha, código, impressão digital, certificado, uma combinação de declarações sobre o usuário que são verdadeiras ou uma combinação dessas coisas usadas juntas.</span><span class="sxs-lookup"><span data-stu-id="6d706-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="6d706-106">AUthN é um processo para provar que você é quem diz ser.</span><span class="sxs-lookup"><span data-stu-id="6d706-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="6d706-107">A autorização (AuthZ) se preocupa com o que você tem acesso depois de provar quem é.</span><span class="sxs-lookup"><span data-stu-id="6d706-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="6d706-108">Ele determina o que você tem permissão para ver, editar e acessar de outra forma.</span><span class="sxs-lookup"><span data-stu-id="6d706-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="6d706-109">Por exemplo, você pode ter um acesso poderoso de Administrador de Conjunto de Sites ao SharePoint Online, mas se mudar para outra carga de trabalho online, como o Skype for Business Online, você pode ter privilégios para solucionar problemas do usuário, não alterar a configuração do servidor ou servidores.</span><span class="sxs-lookup"><span data-stu-id="6d706-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="6d706-110">Em uma terceira carga de trabalho, como o Exchange Online, você pode ter apenas o acesso médio do usuário.</span><span class="sxs-lookup"><span data-stu-id="6d706-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="6d706-111">A AuthZ verifica o que e quanto acesso você tem a serviços/cargas de carga, aplicativos, arquivos e outros dados.</span><span class="sxs-lookup"><span data-stu-id="6d706-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="6d706-112">Nossos exemplos envolvem propriedades online como o SharePoint e o Exchange online, mas os processos de AuthN e AuthZ funcionam no local e em um local híbrido da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="6d706-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="6d706-113">Por fim, ferramentas como o AAD Connect e o ADFS se envolvem na história da AuthN e do AuthZ sincronizando contas locais e senhas no AD da nuvem (que é o Azure AD) ou atrapalhando o fluxo do AuthZ para que um usuário não seja frequentemente solicitado a solicitar suas credenciais, digamos, ao alternar entre cargas de trabalho na nuvem, criando cenários de Sign-On simples.</span><span class="sxs-lookup"><span data-stu-id="6d706-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="6d706-114">Mas eles não são, em si, responsáveis por AuthN ou AuthZ, apenas parte da mecânica.</span><span class="sxs-lookup"><span data-stu-id="6d706-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="6d706-115">Hoje, muitas tecnologias consideram esses processos (AuthN e AuthZ) como um mecanismo, e você ouvirá muitas referências ao processo de autenticação que também incluem autorização neles.</span><span class="sxs-lookup"><span data-stu-id="6d706-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="6d706-116">É importante lembrar que a primeira etapa no acesso do usuário é a AuthN, provando que você é quem diz ser e que a AuthZ usa o conhecimento de quem o usuário é para determinar ao que ele tem acesso (como você verá com a Autorização Aberta ou o OAuth).</span><span class="sxs-lookup"><span data-stu-id="6d706-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="6d706-117">Tópicos de planejamento de autenticação e autorização</span><span class="sxs-lookup"><span data-stu-id="6d706-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="6d706-118">Como usar a Autenticação Moderna (ADAL) com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="6d706-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="6d706-119">Topologias do Skype for Business compatíveis com a Autenticação Moderna</span><span class="sxs-lookup"><span data-stu-id="6d706-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="6d706-120">Planejando desativar os métodos de autenticação herdam interna e externamente para sua rede.</span><span class="sxs-lookup"><span data-stu-id="6d706-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

