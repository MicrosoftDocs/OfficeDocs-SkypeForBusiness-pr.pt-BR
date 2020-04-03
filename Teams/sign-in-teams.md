---
title: Entrar no Microsoft Teams usando a autenticação moderna
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: ''
description: Como entrar no Microsoft Teams usando a autenticação moderna. Inclui como ignorar automaticamente a adição do nome do usuário UPN quando os usuários entram usando uma configuração que instrui o Windows para ignorar o UPN.
localization_priority: Priority
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: f86568f92f2b758ae48062c84b330461743ef178
ms.sourcegitcommit: 8665603fae8408ccbc083dd59cb01936ebe96c58
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43116637"
---
<a name="sign-in-to-microsoft-teams-using-modern-authentication"></a><span data-ttu-id="95b82-104">Entrar no Microsoft Teams usando a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="95b82-104">Sign in to Microsoft Teams using modern authentication</span></span>
==========================

<span data-ttu-id="95b82-105">O Microsoft Teams usa autenticação moderna para manter a experiência de inscrição simples e segura.</span><span class="sxs-lookup"><span data-stu-id="95b82-105">Microsoft Teams uses modern authentication to keep the sign-in experience simple and secure.</span></span> <span data-ttu-id="95b82-106">Para ver como os usuários entram no Teams, leia [Entrar no Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span><span class="sxs-lookup"><span data-stu-id="95b82-106">To see how users sign in to Teams, read [Sign in to Teams](https://support.office.com/article/sign-in-to-teams-ea4b1443-d11b-4791-8ae1-9977e7723055).</span></span>

## <a name="how-modern-authentication-works"></a><span data-ttu-id="95b82-107">Como funciona a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="95b82-107">How modern authentication works</span></span>

<span data-ttu-id="95b82-108">A autenticação moderna é um processo que permite que o Teams saiba que os usuários já inseriram suas credenciais (como e-mail e senha de trabalho) em outro local e não devem ser obrigados a digitá-las novamente para iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="95b82-108">Modern authentication is a process that lets Teams know that users have already entered their credentials (like their work email and password) elsewhere, and they shouldn't be required to enter them again to start the app.</span></span> <span data-ttu-id="95b82-109">A experiência variará dependendo de alguns fatores, como se os usuários estiverem trabalhando no Windows ou em um Mac.</span><span class="sxs-lookup"><span data-stu-id="95b82-109">The experience will vary depending on a couple factors, like if users are working in Windows or on a Mac.</span></span> <span data-ttu-id="95b82-110">Também variará dependendo de sua organização ter ativado a autenticação de fator único ou a autenticação de multifator (a autenticação multifator geralmente envolve a verificação de credenciais por telefone, fornecendo um código exclusivo, a inserção de um PIN ou a impressão digital).</span><span class="sxs-lookup"><span data-stu-id="95b82-110">It will also vary depending on whether your organization has enabled single-factor authentication or multi-factor authentication (multi-factor authentication usually involves verifying credentials via a phone, providing a unique code, entering a PIN, or presenting a thumbprint).</span></span> <span data-ttu-id="95b82-111">Este é um resumo de cada cenário de autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="95b82-111">Here's a rundown of each modern authentication scenario.</span></span>

### <a name="windows-users"></a><span data-ttu-id="95b82-112">Usuários do Windows</span><span class="sxs-lookup"><span data-stu-id="95b82-112">Windows users</span></span> 

- <span data-ttu-id="95b82-113">Se os usuários já tiverem entrado em outros aplicativos do Office por meio da conta do Office 365 Enterprise, quando iniciarem o Teams, serão direcionados diretamente para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="95b82-113">If users have already signed in to other Office apps through their Office 365 Enterprise account, when they start Teams they're taken straight to the app.</span></span> <span data-ttu-id="95b82-114">Não é necessário que eles insiram suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="95b82-114">There's no need for them to enter their credentials.</span></span>

- <span data-ttu-id="95b82-115">Se os usuários não estiverem conectados à conta do Office 365 Enterprise em nenhum outro lugar, ao iniciarem o Teams, será solicitado que forneçam autenticação de fator único ou multifator (SFA ou MFA), dependendo do que sua organização decidiu que eles gostariam que o processo envolvesse.</span><span class="sxs-lookup"><span data-stu-id="95b82-115">If users are not signed in to their Office 365 Enterprise account anywhere else, when they start Teams, they're asked to provide either single-factor or multi-factor authentication (SFA or MFA), depending on what your organization has decided they'd like the process to entail.</span></span>

- <span data-ttu-id="95b82-116">Se os usuários estiverem conectados a um computador ingressado no domínio, quando iniciarem o Teams, poderão ser solicitados a executar mais uma etapa de autenticação, dependendo se sua organização optou por exigir MFA ou se o computador já exige que o MFA faça logon.</span><span class="sxs-lookup"><span data-stu-id="95b82-116">If users are signed in to a domain-joined computer, when they start Teams, they might be asked to go through one more authentication step, depending on whether your organization opted to require MFA or if their computer already requires MFA to sign in.</span></span> <span data-ttu-id="95b82-117">Se o computador deles já exigir MFA para entrar, quando eles abrirem o Teams, o aplicativo será iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="95b82-117">If their computer already requires MFA to sign in, when they open up Teams, the app automatically starts.</span></span>

- <span data-ttu-id="95b82-118">Se os usuários estiverem conectados a um computador ingressado no domínio e você **não quer que o nome de usuário seja preenchido previamente na tela de entrada do Teams**, os administradores poderão definir o seguinte registro do Windows para desativar o pré-preenchimento do nome do usuário (UPN):</span><span class="sxs-lookup"><span data-stu-id="95b82-118">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="95b82-119">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="95b82-119">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="95b82-120">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="95b82-120">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="95b82-121">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="95b82-121">0x00000001 (1)</span></span>

    > [!NOTE]
    > <span data-ttu-id="95b82-122">Pular ou ignorar o pré-preenchimento do nome do usuário para nomes de usuários que terminam com ".local" ou ".corp" está ativado por padrão, por isso, não é necessário definir uma chave de registro para desativá-los.</span><span class="sxs-lookup"><span data-stu-id="95b82-122">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span> 


### <a name="mac-users"></a><span data-ttu-id="95b82-123">Usuários do Mac</span><span class="sxs-lookup"><span data-stu-id="95b82-123">Mac users</span></span> 

<span data-ttu-id="95b82-124">Quando os usuários iniciam o Teams, o computador não consegue extrair credenciais da conta do Office 365 Enterprise ou de qualquer outro aplicativo do Office.</span><span class="sxs-lookup"><span data-stu-id="95b82-124">When users start Teams, their computer won't be able to pull their credentials from their Office 365 Enterprise account or any of their other Office applications.</span></span> <span data-ttu-id="95b82-125">Em vez disso, eles verão um aviso solicitando o SFA ou MFA (dependendo das configurações da sua organização).</span><span class="sxs-lookup"><span data-stu-id="95b82-125">Instead, they'll see a prompt asking them for SFA or MFA (depending on your organization's settings).</span></span> <span data-ttu-id="95b82-126">Quando os usuários inserem suas credenciais, eles não precisarão fornecê-las novamente.</span><span class="sxs-lookup"><span data-stu-id="95b82-126">Once users enter their credentials, they won't be required to provide them again.</span></span> <span data-ttu-id="95b82-127">A partir desse ponto em diante, o Teams será iniciado automaticamente sempre que estiverem trabalhando no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="95b82-127">From that point on, Teams automatically starts whenever they're working on the same computer.</span></span>

## <a name="switching-accounts-after-completing-modern-authentication"></a><span data-ttu-id="95b82-128">Alternar contas após concluir a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="95b82-128">Switching accounts after completing modern authentication</span></span>

<span data-ttu-id="95b82-129">Se os usuários estiverem trabalhando em um computador ingressado no domínio (por exemplo, se o locatário tiver ativado o Kerberos), eles não poderão trocar de conta de usuário depois de concluir a autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="95b82-129">If users are working on a domain-joined computer (for example, if their tenant has enabled Kerberos), they cannot switch user accounts once they've completed modern authentication.</span></span> <span data-ttu-id="95b82-130">Se os usuários não estiverem trabalhando em um computador ingressado no domínio, eles poderão alternar contas.</span><span class="sxs-lookup"><span data-stu-id="95b82-130">If users are not working on a domain-joined computer, they can switch accounts.</span></span>

## <a name="signing-out-of-teams-after-completing-modern-authentication"></a><span data-ttu-id="95b82-131">Sair do Teams após concluir a autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="95b82-131">Signing out of Teams after completing modern authentication</span></span>
<span data-ttu-id="95b82-132">Para sair do Teams, os usuários podem clicar na imagem do perfil na parte superior do aplicativo e, em seguida, selecionar **Sair**. Eles também podem clicar com o botão direito do mouse no ícone do aplicativo na barra de tarefas e, em seguida, selecionar **Fazer logoff**. Depois de sair do Teams, eles precisam inserir suas credenciais novamente para iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="95b82-132">To sign out of Teams, users can click their profile picture at the top of the app, and then select **Sign out**. They can also right-click the app icon in their taskbar, and then select **Log out**. Once they've sign out of Teams, they need to enter their credentials again to launch the app.</span></span>

## <a name="urls-and-ip-address-ranges"></a><span data-ttu-id="95b82-133">URLs e intervalos de endereços IP</span><span class="sxs-lookup"><span data-stu-id="95b82-133">URLs and IP address ranges</span></span>
<span data-ttu-id="95b82-134">O Teams exige conectividade com a Internet.</span><span class="sxs-lookup"><span data-stu-id="95b82-134">Teams requires connectivity to the Internet.</span></span> <span data-ttu-id="95b82-135">Para entender os pontos de extremidade que devem ser acessados pelos clientes que usam o Teams nos planos do Office 365, no Governo e em outras nuvens, leia [URLs e intervalos de endereços IP do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="95b82-135">To understand endpoints that should be reachable for customers using Teams in Office 365 plans, Government and other clouds, read [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="95b82-136">O Teams atualmente exige o acesso (porta TCP 443) para o serviço Google ssl.gstatic.com (https://ssl.gstatic.com) para todos os usuários; tal exigência é obrigatória mesmo que você não esteja usando o Gstatic.</span><span class="sxs-lookup"><span data-stu-id="95b82-136">Teams presently requires access (TCP port 443) to the Google ssl.gstatic.com service (https://ssl.gstatic.com) for all users; this is true even if you're not using Gstatic.</span></span> <span data-ttu-id="95b82-137">O Teams removerá esse requisito em breve (início de 2020), e atualizaremos este artigo de forma adequada neste momento.</span><span class="sxs-lookup"><span data-stu-id="95b82-137">Teams will remove this requirement soon (early 2020), and we'll update this article accordingly at that time.</span></span>

## <a name="troubleshooting-modern-authentication"></a><span data-ttu-id="95b82-138">Solução de problemas de autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="95b82-138">Troubleshooting modern authentication</span></span>

<span data-ttu-id="95b82-139">A autenticação moderna está disponível para todas as organizações que usam o Teams; portanto, se os usuários não puderem concluir o processo, pode haver algo errado com o seu domínio ou a conta do Office 365 Enterprise da sua organização.</span><span class="sxs-lookup"><span data-stu-id="95b82-139">Modern authentication is available for every organization that uses Teams, so if users are not able to complete the process, there might be something wrong with your domain or your organization's Office 365 Enterprise account.</span></span> 

<span data-ttu-id="95b82-140">Para saber mais, confira [Por que estou com problemas para entrar no Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span><span class="sxs-lookup"><span data-stu-id="95b82-140">For more information, see [Why am I having trouble signing in to Microsoft Teams?](https://support.office.com/article/why-am-i-having-trouble-signing-in-to-microsoft-teams-a02f683b-61a3-4008-9447-ee60c5593b0f)</span></span>

