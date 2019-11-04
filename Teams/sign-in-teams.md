---
title: Entrar no Microsoft Teams usando a autenticação moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/15/2018
audience: Admin
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Como entrar no Microsoft Teams usando a autenticação moderna.
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a5698058cbfecd62f92cfe9f198657f7c280deff
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37563118"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="bbd2d-103">Entrar no Microsoft Teams usando a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="bbd2d-103">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="bbd2d-104">O Microsoft Teams usa autenticação moderna para manter a experiência de entrada simples e segura.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-104">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="bbd2d-105">Para ver como os usuários entram no Microsoft Teams, leia entrar no Microsoft [Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span><span class="sxs-lookup"><span data-stu-id="bbd2d-105">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="bbd2d-106">Como funciona a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="bbd2d-106">How modern authentication works</span></span>

<span data-ttu-id="bbd2d-107">A autenticação moderna é um processo que permite que as equipes saibam que os usuários já inseriram suas credenciais (como o email e a senha de trabalho) em outro lugar, e não devem ser necessárias para inseri-las novamente para iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-107">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="bbd2d-108">A experiência irá variar dependendo de alguns fatores, como se os usuários estiverem trabalhando no Windows ou em um Mac.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-108">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="bbd2d-109">Isso também varia de acordo com a existência da autenticação de fator único ou da autenticação multifator da sua organização (autenticação multifator geralmente envolve a verificação de credenciais por meio de um telefone, o fornecimento de um código exclusivo, a inserção de um pino ou Apresentando uma impressão digital).</span><span class="sxs-lookup"><span data-stu-id="bbd2d-109">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="bbd2d-110">Aqui está um resumo de cada cenário de autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-110">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="bbd2d-111">Usuários do Windows:</span><span class="sxs-lookup"><span data-stu-id="bbd2d-111">Windows users</span></span> 

- <span data-ttu-id="bbd2d-112">Se os usuários já entrarem em outros aplicativos do Office por meio da sua conta empresarial do Office 365, quando eles iniciarem as equipes, eles serão colocados diretamente no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-112">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="bbd2d-113">Não é necessário inserir suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-113">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="bbd2d-114">Se os usuários não estiverem conectados à sua conta empresarial do Office 365 em qualquer outro lugar, quando iniciarem o Teams, eles serão solicitados a fornecer autenticação de fator único ou multifator (SFA ou MFA), dependendo do que a sua organização decidiu que gostaria da processo para implicar.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-114">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="bbd2d-115">Se os usuários estiverem conectados a um computador associado a um domínio, quando iniciarem o Teams, eles poderão ser solicitados a passar por mais uma etapa de autenticação, dependendo se a sua organização optou por exigir MFA ou se o computador já precisa de uma solicitação de conexão.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-115">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="bbd2d-116">Se o computador já precisa de uma MFA para entrar, quando ele abre equipes, o aplicativo é iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-116">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

### <a name="mac-users"></a><span data-ttu-id="bbd2d-117">Usuários do Mac</span><span class="sxs-lookup"><span data-stu-id="bbd2d-117">Mac users</span></span> 

<span data-ttu-id="bbd2d-118">Quando os usuários iniciarem o Microsoft Teams, o computador não poderá receber credenciais da conta empresarial do Office 365 ou de qualquer um dos outros aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-118">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="bbd2d-119">Em vez disso, eles verão um prompt solicitando o SFA ou o MFA (dependendo das configurações da sua organização).</span><span class="sxs-lookup"><span data-stu-id="bbd2d-119">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="bbd2d-120">Uma vez que os usuários inserem suas credenciais, não será preciso fornecê-las novamente.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-120">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="bbd2d-121">Desse ponto em diante, o Teams é iniciado automaticamente sempre que estiverem trabalhando no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-121">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="bbd2d-122">Alternar entre contas após concluir a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="bbd2d-122">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="bbd2d-123">Se os usuários estiverem trabalhando em um computador associado a um domínio (por exemplo, se o locatário tiver habilitado o Kerberos), eles não poderão alternar entre contas de usuário depois que concluírem a autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-123">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="bbd2d-124">Se os usuários não estiverem trabalhando em um computador associado a um domínio, eles poderão mudar de conta.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-124">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-microsoft-teams-after-completing-modern-authentication"></a><span data-ttu-id="bbd2d-125">Saindo do Microsoft Teams depois de concluir a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="bbd2d-125">Signing out of Microsoft Teams after completing modern authentication</span></span>
<span data-ttu-id="bbd2d-126">Para sair do Teams, os usuários podem clicar na imagem do perfil na parte superior do aplicativo e, em seguida **, selecione sair**. Eles também podem clicar com o botão direito do mouse no ícone do aplicativo na barra de tarefas e, em seguida, selecionar **logout**. Depois de desconectarem-se do Teams, será necessário inserir suas credenciais novamente para iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-126">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="bbd2d-127">Solução de problemas de autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="bbd2d-127">Troubleshooting modern authentication</span></span>

<span data-ttu-id="bbd2d-128">A autenticação moderna está disponível para cada organização que usa o Teams, portanto, se os usuários não conseguem completar o processo, pode haver algo errado com o seu domínio ou com a conta corporativa do Office 365 da sua organização.</span><span class="sxs-lookup"><span data-stu-id="bbd2d-128">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="bbd2d-129">Para obter mais informações, consulte [por que estou tendo problemas para entrar no Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span><span class="sxs-lookup"><span data-stu-id="bbd2d-129">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f).</span></span>

