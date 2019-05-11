---
title: Integração entre o Skype para Business Online e Exchange server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Configurando o OAuth a autenticação entre o Exchange no local e Skype para Business Online permite que o Skype para recursos de integração do Exchange e de negócios descritos no suporte ao recurso.
ms.openlocfilehash: c6a3819c9ec6ae0c207307a23f67bf04e4f07ac0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894236"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a><span data-ttu-id="715e7-103">Configure a integração entre o Skype para negócios on-line ou equipes da Microsoft e o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="715e7-103">Configure Integration between Skype for Business Online or Microsoft Teams and Exchange Server</span></span> 

<span data-ttu-id="715e7-104">Configurando a integração entre o Exchange server e do Skype para Business Online permite que o Skype para recursos de integração do Exchange e de negócios descritos em [suporte de recurso](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="715e7-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="715e7-105">Este tópico se aplica a integração com o Exchange Server 2013 por meio de 2019.</span><span class="sxs-lookup"><span data-stu-id="715e7-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="715e7-106">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="715e7-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="715e7-107">Tempo estimado para concluir esta tarefa: 15 minutos</span><span class="sxs-lookup"><span data-stu-id="715e7-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="715e7-108">Você precisa receber permissões antes de realizar esse procedimento ou procedimentos.</span><span class="sxs-lookup"><span data-stu-id="715e7-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="715e7-109">Para ver quais permissões você precisa, consulte o tópico [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="715e7-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="715e7-110">Para obter informações sobre atalhos de teclado que possam se aplicar aos procedimentos neste tópico, consulte [atalhos de teclado no Centro de administração do Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="715e7-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="715e7-111">Configure a integração entre o Exchange Server e do O365</span><span class="sxs-lookup"><span data-stu-id="715e7-111">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="715e7-112">Etapa 1: Configurar a autenticação OAuth entre o Exchange Server e do O365</span><span class="sxs-lookup"><span data-stu-id="715e7-112">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="715e7-113">Execute as etapas no seguinte artigo:</span><span class="sxs-lookup"><span data-stu-id="715e7-113">Perform the steps in the following article:</span></span>

[<span data-ttu-id="715e7-114">Configurar a autenticação OAuth entre organizações do Exchange e o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="715e7-114">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a><span data-ttu-id="715e7-115">Etapa 2: Criar uma nova conta de usuário de email para o Skype para Business Online ou aplicativo de parceiro de equipes</span><span class="sxs-lookup"><span data-stu-id="715e7-115">Step 2: Create a new Mail User account for the Skype for Business Online or Teams Partner Application</span></span>

<span data-ttu-id="715e7-116">Esta etapa é realizada no servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="715e7-116">This step is done on the Exchange server.</span></span> <span data-ttu-id="715e7-117">Ela criará um usuário de caixa de correio e atribuirá os direitos apropriados da função de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="715e7-117">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="715e7-118">Essa conta será então usada na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="715e7-118">This account will then be used in the next step.</span></span>

<span data-ttu-id="715e7-119">Especifique um domínio verificado para sua organização do Exchange.</span><span class="sxs-lookup"><span data-stu-id="715e7-119">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="715e7-120">Esse domínio deve ser o mesmo usado como o domínio SMTP primário usado para as contas do Exchange local.</span><span class="sxs-lookup"><span data-stu-id="715e7-120">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="715e7-121">Este domínio é conhecido como \<seu domínio verificado\> no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="715e7-121">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="715e7-122">Além disso, o \<DomainControllerFQDN\> deve ser o FQDN de um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="715e7-122">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="715e7-123">Esse comando ocultará o novo usuário da caixa de correio das listas de endereços.</span><span class="sxs-lookup"><span data-stu-id="715e7-123">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="715e7-124">Esses dois próximos comandos atribuirão a função de gerenciamento de UserApplication e ArchiveApplication a esta nova conta.</span><span class="sxs-lookup"><span data-stu-id="715e7-124">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a><span data-ttu-id="715e7-125">Etapa 3: Criar e habilitar um aplicativo de parceiro do Skype para Business Online ou equipes</span><span class="sxs-lookup"><span data-stu-id="715e7-125">Step 3: Create and enable a Partner Application for Skype for Business Online or Teams</span></span>

<span data-ttu-id="715e7-126">Crie um novo aplicativo parceiro e use a conta que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="715e7-126">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="715e7-127">Execute o seguinte comando no Exchange PowerShell em seu local de organização do Exchange.</span><span class="sxs-lookup"><span data-stu-id="715e7-127">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a><span data-ttu-id="715e7-128">Verifique se a operação foi realizada com sucesso</span><span class="sxs-lookup"><span data-stu-id="715e7-128">Verify your success</span></span>

<span data-ttu-id="715e7-129">Verifique se a configuração está correta verificando que alguns dos recursos estão funcionando com êxito.</span><span class="sxs-lookup"><span data-stu-id="715e7-129">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="715e7-130">Confirme se dois usuários de equipes betweeen com Exchange Server 2016 ou caixas de correio 2019 a delegação de calendário do Outlook funciona.</span><span class="sxs-lookup"><span data-stu-id="715e7-130">Confirm Outlook Calendar delegation works betweeen two Teams users with Exchange Server 2016 or 2019 mailboxes.</span></span>

2. <span data-ttu-id="715e7-131">Confirme histórico da conversa para clientes móveis é visível na pasta Histórico da conversa do Outlook.</span><span class="sxs-lookup"><span data-stu-id="715e7-131">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

<span data-ttu-id="715e7-132">Como alternativa, examine o tráfego.</span><span class="sxs-lookup"><span data-stu-id="715e7-132">Alternately, look at your traffic.</span></span> <span data-ttu-id="715e7-133">O tráfego em um handshake OAuth é realmente característica (e não se parece com a autenticação básica), especialmente ao redor territórios, onde você vai começar a ver o tráfego de emissor parecida com esta: 00000004-0000-0ff1-ce00-000000000000 @ (às vezes com uma / antes o sinal @), em que estão sendo passados tokens.</span><span class="sxs-lookup"><span data-stu-id="715e7-133">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="715e7-134">Você não verá um nome de usuário ou senha, que é o ponto do OAuth.</span><span class="sxs-lookup"><span data-stu-id="715e7-134">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="715e7-135">Mas você verá o emissor 'Temporária' – nesse caso, '4' é Skype para negócios – e o território de sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="715e7-135">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="715e7-136">Se você quiser ter certeza de que você estiver usando o OAuth com êxito, certifique-se de que você sabe o que esperar e quando já souber o que o tráfego deve se parecer com.</span><span class="sxs-lookup"><span data-stu-id="715e7-136">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="715e7-137">Caso [aqui está o que esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aqui está um bem standard [exemplo de tráfego de OAuth em um aplicativo da Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (realmente úteis para mensagens lidas, embora não use Refresh tokens) e existem extensões Fiddler que permitirá que você procure em seu OAuth JWT (JSON Token de Web).</span><span class="sxs-lookup"><span data-stu-id="715e7-137">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="715e7-138">Aqui está um [exemplo de configuração de um](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), mas você pode usar qualquer ferramenta de rastreamento de rede que você deseja realizar esse processo.</span><span class="sxs-lookup"><span data-stu-id="715e7-138">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="715e7-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="715e7-139">Related topics</span></span>

[<span data-ttu-id="715e7-140">Configurar a autenticação OAuth entre organizações do Exchange e o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="715e7-140">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
