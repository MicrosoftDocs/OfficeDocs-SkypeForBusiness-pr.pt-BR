---
title: Integração entre o Skype for Business Online e o Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: A configuração da autenticação OAuth entre o Exchange local e o Skype for Business Online permite que os recursos de integração do Skype for Business e do Exchange descritos em suporte a recursos.
ms.openlocfilehash: be1fd4ae0c1a1046a8da1d9a30550ac238a4034a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278123"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a><span data-ttu-id="b918d-103">Configurar a integração entre o Skype for Business online ou o Microsoft Teams e o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="b918d-103">Configure Integration between Skype for Business Online or Microsoft Teams and Exchange Server</span></span> 

<span data-ttu-id="b918d-104">A configuração da integração entre o Exchange Server e o Skype for Business Online permite que os recursos de integração do Skype for Business e do Exchange descritos em [suporte a recursos](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="b918d-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="b918d-105">Este tópico se aplica à integração com o Exchange Server 2013 a 2019.</span><span class="sxs-lookup"><span data-stu-id="b918d-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b918d-106">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="b918d-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b918d-107">Tempo estimado para concluir esta tarefa: 15 minutos</span><span class="sxs-lookup"><span data-stu-id="b918d-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="b918d-108">Você precisa receber permissões antes de realizar esse procedimento ou procedimentos.</span><span class="sxs-lookup"><span data-stu-id="b918d-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="b918d-109">Para ver quais permissões você precisa, consulte o tópico [permissões de infraestrutura do Shell e do Exchange](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="b918d-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="b918d-110">Para obter informações sobre os atalhos de teclado que podem ser aplicáveis aos procedimentos deste tópico, consulte [atalhos de teclado no centro de administração do Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="b918d-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="b918d-111">Configurar a integração entre o Exchange Server e o O365</span><span class="sxs-lookup"><span data-stu-id="b918d-111">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="b918d-112">Etapa 1: configurar a autenticação OAuth entre o Exchange Server e o O365</span><span class="sxs-lookup"><span data-stu-id="b918d-112">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="b918d-113">Execute as etapas do seguinte artigo:</span><span class="sxs-lookup"><span data-stu-id="b918d-113">Perform the steps in the following article:</span></span>

[<span data-ttu-id="b918d-114">Configurar a autenticação OAuth entre organizações Exchange e Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b918d-114">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a><span data-ttu-id="b918d-115">Etapa 2: criar uma nova conta de usuário de email para o Skype for Business online ou o aplicativo para parceiros de equipe</span><span class="sxs-lookup"><span data-stu-id="b918d-115">Step 2: Create a new Mail User account for the Skype for Business Online or Teams Partner Application</span></span>

<span data-ttu-id="b918d-116">Esta etapa é feita no Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="b918d-116">This step is done on the Exchange server.</span></span> <span data-ttu-id="b918d-117">Ela criará um usuário de caixa de correio e atribuirá os direitos apropriados da função de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="b918d-117">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="b918d-118">Essa conta será então usada na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="b918d-118">This account will then be used in the next step.</span></span>

<span data-ttu-id="b918d-119">Especifique um domínio verificado para sua organização do Exchange.</span><span class="sxs-lookup"><span data-stu-id="b918d-119">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="b918d-120">Esse domínio deve ser o mesmo usado como o domínio SMTP principal usado para as contas do Exchange no local.</span><span class="sxs-lookup"><span data-stu-id="b918d-120">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="b918d-121">Esse domínio é chamado \<de domínio\> verificado no procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="b918d-121">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="b918d-122">Além disso, \<o\> DOMAINCONTROLLERFQDN deve ser o FQDN de um controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="b918d-122">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="b918d-123">Esse comando ocultará o novo usuário da caixa de correio das listas de endereços.</span><span class="sxs-lookup"><span data-stu-id="b918d-123">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="b918d-124">Esses dois próximos comandos atribuirão a função de gerenciamento de UserApplication e ArchiveApplication a esta nova conta.</span><span class="sxs-lookup"><span data-stu-id="b918d-124">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a><span data-ttu-id="b918d-125">Etapa 3: criar e habilitar um aplicativo parceiro para o Skype for Business online ou o Teams</span><span class="sxs-lookup"><span data-stu-id="b918d-125">Step 3: Create and enable a Partner Application for Skype for Business Online or Teams</span></span>

<span data-ttu-id="b918d-126">Crie um novo aplicativo parceiro e use a conta que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="b918d-126">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="b918d-127">Execute o seguinte comando no PowerShell do Exchange em sua organização do Exchange local.</span><span class="sxs-lookup"><span data-stu-id="b918d-127">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a><span data-ttu-id="b918d-128">Verifique se a operação foi realizada com sucesso</span><span class="sxs-lookup"><span data-stu-id="b918d-128">Verify your success</span></span>

<span data-ttu-id="b918d-129">Verifique se a configuração está correta verificando se alguns dos recursos estão funcionando com êxito.</span><span class="sxs-lookup"><span data-stu-id="b918d-129">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="b918d-130">Confirmar a delegação do calendário do Outlook funciona betweeen dois usuários do teams com as caixas de correio do Exchange Server 2016 ou do 2019.</span><span class="sxs-lookup"><span data-stu-id="b918d-130">Confirm Outlook Calendar delegation works betweeen two Teams users with Exchange Server 2016 or 2019 mailboxes.</span></span>

2. <span data-ttu-id="b918d-131">Confirme se o histórico de conversas para clientes móveis está visível na pasta Histórico de conversas do Outlook.</span><span class="sxs-lookup"><span data-stu-id="b918d-131">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

<span data-ttu-id="b918d-132">Como alternativa, examine seu tráfego.</span><span class="sxs-lookup"><span data-stu-id="b918d-132">Alternately, look at your traffic.</span></span> <span data-ttu-id="b918d-133">O tráfego em um handshake OAuth é realmente distintivo (e não se parece com autenticação básica), especialmente em relação a territórios, onde você começará a ver o tráfego do emissor que tem a seguinte aparência: 00000004-0000-0ff1-ce00-000000000000 @ (às vezes com/antes o símbolo @), nos tokens que estão sendo passados.</span><span class="sxs-lookup"><span data-stu-id="b918d-133">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="b918d-134">Você não verá um nome de usuário ou senha, que é o ponto de OAuth.</span><span class="sxs-lookup"><span data-stu-id="b918d-134">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="b918d-135">Mas você verá o emissor "Office" – neste caso, ' 4 ' é o Skype for Business – e o território da sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="b918d-135">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="b918d-136">Se você quiser ter certeza de que está usando o OAuth com êxito, verifique se sabe o que esperar e saiba para que tal tráfego deve ser exibido.</span><span class="sxs-lookup"><span data-stu-id="b918d-136">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="b918d-137">Portanto, [Veja o que esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aqui está um exemplo bem padrão [de tráfego OAuth em um aplicativo da Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (muito útil para ler, embora não use tokens de atualização), e existem extensões Fiddler que permitem que você examine seu JWT OAuth (JSON Token da Web).</span><span class="sxs-lookup"><span data-stu-id="b918d-137">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="b918d-138">Veja um [exemplo de](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)como configurar um, mas você pode usar qualquer ferramenta de rastreamento de rede que você queira para empreender esse processo.</span><span class="sxs-lookup"><span data-stu-id="b918d-138">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b918d-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b918d-139">Related topics</span></span>

[<span data-ttu-id="b918d-140">Configurar a autenticação OAuth entre organizações Exchange e Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b918d-140">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
