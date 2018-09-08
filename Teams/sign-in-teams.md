---
title: Entrar com equipes da Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/23/2018
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Orientação para entrar no Microsoft Teams usando autenticação moderna.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e44b05bd0daed8867247512d38f22b764351127d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882026"
---
<a name="sign-in-to-microsoft-teams"></a><span data-ttu-id="c8ae9-103">Entrar com equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c8ae9-103">Sign in to Microsoft Teams</span></span>
==========================

<span data-ttu-id="c8ae9-104">Teams da Microsoft usa autenticação moderna para manter a experiência de entrada, simples e segura.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="c8ae9-105">Moderno como funciona a autenticação</span><span class="sxs-lookup"><span data-stu-id="c8ae9-105">How modern authentication works</span></span>

<span data-ttu-id="c8ae9-106">Autenticação moderna é um processo que permite que as equipes saber que os usuários já foram inseridos suas credenciais (como seu trabalho email e senha) em outro lugar e eles não devem ser necessário inseri-las novamente para iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-106">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="c8ae9-107">A experiência variará dependendo de dois fatores, como se os usuários estão trabalhando no Windows ou em um Mac.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-107">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="c8ae9-108">Ele também irá variar dependendo se a sua organização tiver habilitado a autenticação de fator único ou a autenticação multifator (geralmente, a autenticação multifator envolve verificando credenciais por meio de um telefone, fornecendo um código exclusivo, inserindo um PIN, ou Apresentando uma impressão digital).</span><span class="sxs-lookup"><span data-stu-id="c8ae9-108">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="c8ae9-109">Aqui está um resumo de cada cenário de autenticação moderno.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-109">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="c8ae9-110">Usuários do Windows:</span><span class="sxs-lookup"><span data-stu-id="c8ae9-110">Windows users</span></span> 

- <span data-ttu-id="c8ae9-111">Se os usuários já tenham entrado em para outros aplicativos do Office por meio de sua conta do Office 365 Enterprise, quando eles começarem a equipes serão levados retas para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-111">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="c8ae9-112">Não é necessário para que eles possam Insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-112">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="c8ae9-113">Se os usuários não estiver conectados à sua conta do Office 365 Enterprise em outros lugares, quando eles começarem a equipes, ele são solicitados a fornecer autenticação fator único ou vários fator (SFA ou MFA), dependendo de qual sua organização tiver decidido gostariam de processo envolve.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-113">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="c8ae9-114">Se os usuários estiver conectados a um computador associado ao domínio, quando eles começarem a equipes, eles podem ser solicitados atravessar uma etapa de autenticação mais, dependendo se a sua organização tiver optado para exigir MFA ou se o seu computador já exige MFA entrar.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-114">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="c8ae9-115">Se seu computador já exigir MFA entrar, quando eles abrem backup equipes, o aplicativo automaticamente inicia.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-115">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="c8ae9-116">Usuários do Mac</span><span class="sxs-lookup"><span data-stu-id="c8ae9-116">Mac users</span></span> 

<span data-ttu-id="c8ae9-117">Quando os usuários iniciam equipes, seu computador não poderá receber suas credenciais de sua conta do Office 365 Enterprise ou para qualquer um dos seus outros aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-117">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="c8ae9-118">Em vez disso, eles verão um aviso perguntando-los para SFA ou MFA (dependendo das configurações da sua organização).</span><span class="sxs-lookup"><span data-stu-id="c8ae9-118">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="c8ae9-119">Depois que os usuários inserirem suas credenciais, eles não seja necessário para fornecer-lhes novamente.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-119">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="c8ae9-120">A partir desse momento, as equipes automaticamente inicia sempre eles estiver trabalhando no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-120">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="c8ae9-121">Alternando contas depois de concluir a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="c8ae9-121">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="c8ae9-122">Se os usuários estão trabalhando em um computador associado ao domínio (por exemplo, se seu locatário tiver habilitado o Kerberos), eles não podem alternar contas de usuário quando concluírem autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-122">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="c8ae9-123">Se os usuários não estiver trabalhando em um computador associado ao domínio, eles podem alternar contas.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-123">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="c8ae9-124">Saindo do Microsoft Teams depois de concluir a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="c8ae9-124">Signing out of Microsoft Teams after completing modern authentication</span></span>

<span data-ttu-id="c8ae9-125">Para sair de equipes, os usuários podem clique em sua foto de perfil, na parte superior do aplicativo e selecione **Sair**. Eles podem também com o botão direito no ícone do aplicativo na sua barra de tarefas e selecione **efetuar logout**. Depois que eles já saírem equipes, elas precisam inserir suas credenciais novamente para iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-125">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="c8ae9-126">Solução de problemas de autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="c8ae9-126">Troubleshooting modern authentication</span></span>

<span data-ttu-id="c8ae9-127">Autenticação moderna está disponível para todas as organizações que usa as equipes, portanto se os usuários não conseguem concluir o processo, pode haver algo errada com seu domínio ou a conta do Office 365 Enterprise da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c8ae9-127">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="c8ae9-128">Para obter mais informações, consulte [por que estou tendo problemas para entrar na Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span><span class="sxs-lookup"><span data-stu-id="c8ae9-128">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

