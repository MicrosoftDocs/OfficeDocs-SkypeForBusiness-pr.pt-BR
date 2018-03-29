---
title: Mover usuários locais para Skype para negócios Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: 'Resumo: Informações sobre como mover usuários locais para Skype para negócios Online.'
ms.openlocfilehash: 9aa4c87d713af437f1fbb81cd23e354792559aa8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a><span data-ttu-id="967f8-103">Mover usuários locais para Skype para negócios Online</span><span class="sxs-lookup"><span data-stu-id="967f8-103">Move on-premises users to Skype for Business Online</span></span>
 
<span data-ttu-id="967f8-104">**Resumo:** Informações sobre como mover os usuários locais para Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="967f8-104">**Summary:** Information about moving on-premises users to Skype for Business Online.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="967f8-105">Os dispositivos Lync Phone Edition DEVEM ser atualizados para o firmware mínimo necessário em seu ambiente local antes de mover para o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="967f8-105">Lync Phone Edition devices MUST be updated to minimum required firmware in your on premises environment PRIOR to moving to Skype for Business Online.</span></span> <span data-ttu-id="967f8-106">Se você mover seus usuários da implantação local para a online antes de atualizar o firmware, eles não conseguirão se conectar usando os seus telefones.</span><span class="sxs-lookup"><span data-stu-id="967f8-106">If you move your users from on-premises to online prior to updating the firmware, users will be unable to connect using their phones.</span></span> <span data-ttu-id="967f8-107">Para corrigir esse problema, os usuários devem ser movidos de volta para o ambiente local para que seus telefones sejam atualizados para o firmware mínimo.</span><span class="sxs-lookup"><span data-stu-id="967f8-107">To correct this problem, users must be moved back to the on premises environment to have their phones updated to the minimum firmware.</span></span> <span data-ttu-id="967f8-108">NÃO TENTE ATUALIZAR PARA O FIRMWARE MÍNIMO OU FAZER A REINICIALIZAÇÃO FORÇADA DO TELEFONE ANTES DE MOVER O USUÁRIO DE VOLTA PARA SEU AMBIENTE LOCAL.</span><span class="sxs-lookup"><span data-stu-id="967f8-108">DO NOT ATTEMPT TO UPDATE TO MINIMUM FIRMWARE OR HARD RESET THE PHONE PRIOR TO MOVING THE USER BACK TO YOUR ON PREMISES ENVIRONMENT.</span></span>
<span data-ttu-id="967f8-109">Se houver uma reinicialização forçada enquanto o dispositivo não estiver no firmware mínimo, o padrão será definido como Autenticação PIN, que não tem suporte no Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="967f8-109">If a hard reset is performed while the device is not at minimum firmware it will default to using PIN Authentication, which is not supported in Skype for Business Online.</span></span> <span data-ttu-id="967f8-110">Para obter mais informações, consulte [Getting telefones para Skype para negócios Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).</span><span class="sxs-lookup"><span data-stu-id="967f8-110">For more information, please refer to [Getting Phones for Skype for Business Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="967f8-111">Esta é uma etapa opcional que é necessária apenas se você estiver movendo usuários locais para Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="967f8-111">This is an optional step that is required only if you are moving on-premises users to Skype for Business Online.</span></span> <span data-ttu-id="967f8-112">Antes de começar mover usuários para Skype para Business Online, verifique se o Skype para Business Online Connector (módulo do Windows PowerShell) é implantado em seus servidores Front-End.</span><span class="sxs-lookup"><span data-stu-id="967f8-112">Before you begin to move users to Skype for Business Online, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="967f8-113">Se não for, você pode baixá-lo no [Centro de download](https://www.microsoft.com/en-us/download/details.aspx?id=39366)da.</span><span class="sxs-lookup"><span data-stu-id="967f8-113">If it isn't, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="967f8-114">Além disso, para preparar seu AD, será necessário configurar o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="967f8-114">Also, to prepare your AD, you'll need to configure Azure AD Connect.</span></span> <span data-ttu-id="967f8-115">A versão do AAD Connect que você usar deve ser a versão 1.0.9125.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="967f8-115">The version of AAD Connect you use must be version 1.0.9125.0 or later.</span></span> <span data-ttu-id="967f8-116">Se você estiver usando uma versão anterior das ferramentas do AAD Connect ou do DirSync, atualize para a versão com suporte.</span><span class="sxs-lookup"><span data-stu-id="967f8-116">If you are using an earlier version of AAD Connect tools or DirSync, please upgrade to the supported version.</span></span> <span data-ttu-id="967f8-117">Você pode atualizar sua instalação atual e manter qualquer regra personalizada que você tenha definido em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="967f8-117">You can upgrade your current installation and maintain any custom rules you have defined in your environment.</span></span>
  
<span data-ttu-id="967f8-118">Mover usuários usando um dos Skype para painel de controle do Business Server ou Skype para Business Server Management Shell em sua implantação no local, mas você deve ter credenciais de administrador para a sua implantação do Office 365.</span><span class="sxs-lookup"><span data-stu-id="967f8-118">You move users using either Skype for Business Server Control Panel or Skype for Business Server Management Shell in your on-premises deployment, but you must have administrator credentials for your Office 365 deployment.</span></span>
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a><span data-ttu-id="967f8-119">Movendo usuários usando o Skype para painel de controle de negócios</span><span class="sxs-lookup"><span data-stu-id="967f8-119">Moving users by using Skype for Business Control Panel</span></span>

### <a name="to-move-a-user-to-skype-for-business-online"></a><span data-ttu-id="967f8-120">Para mover um usuário para Skype para negócios Online</span><span class="sxs-lookup"><span data-stu-id="967f8-120">To move a user to Skype for Business Online</span></span>

1. <span data-ttu-id="967f8-121">Usando uma conta de usuário atribuída à função CsUserAdministrator ou csadministrator, faça logon em qualquer computador em sua implantação interna que tem Skype para Business Server ou, no mínimo Skype para as ferramentas de administração de servidor de negócios instaladas.</span><span class="sxs-lookup"><span data-stu-id="967f8-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment that has Skype for Business Server, or at least Skype for Business Server Admin tools installed.</span></span>
    
2. <span data-ttu-id="967f8-122">No menu Iniciar ou atalho da área de trabalho, abra o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="967f8-122">From the Start menu or desktop shortcut, open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="967f8-123">Você também pode acessar o Skype para painel de controle do Business Server usando a URL do administrador, se você tiver configurado um.</span><span class="sxs-lookup"><span data-stu-id="967f8-123">You can also access the Skype for Business Server Control Panel by using the Admin URL if you have configured one.</span></span>
    
3. <span data-ttu-id="967f8-124">Na barra de navegação esquerda, clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="967f8-124">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="967f8-125">Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário que deseja habilitar e clique em **Localizar**.</span><span class="sxs-lookup"><span data-stu-id="967f8-125">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="967f8-126">Clique no usuário, no menu de **Ação** e, em seguida, clique em **Mover usuários selecionados para o Skype for Business Online**.</span><span class="sxs-lookup"><span data-stu-id="967f8-126">Click the user, then in the **Action** menu, click **Move selected users to Skype for Business Online**.</span></span>
    
6. <span data-ttu-id="967f8-127">Na página **Mover usuários para o Skype for Business Online**, leia as informações e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="967f8-127">On the **Move users to Skype For Business Online** page, read the information and then click **Next**.</span></span>
    
7. <span data-ttu-id="967f8-128">Na próxima página, se não você ainda estiver conectado ao Office 365, clique em **entrar no Office 365**, forneça suas credenciais e clique em **Okey** e em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="967f8-128">On the next page, if you are not yet signed in to Office 365, click **Sign in to Office 365**, provide your credentials, and click **OK** and **Next**.</span></span>
    
8. <span data-ttu-id="967f8-129">Verifique se o número de usuários a serem movidos está correto e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="967f8-129">Confirm that the number of users to be moved is correct, and click **Next**.</span></span>
    
9. <span data-ttu-id="967f8-130">Na próxima página, confira os resultados e clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="967f8-130">On the next page, review the results and click **Close**.</span></span>
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="967f8-131">Movendo usuários usando o Skype do Shell de gerenciamento do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="967f8-131">Moving users by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="967f8-132">Para mover um usuário local para seu Skype para locatário Business Online, execute os cmdlets a seguir no Skype do Shell de gerenciamento do servidor de negócios, utilizando as credenciais de administrador para o seu locatário do Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="967f8-132">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="967f8-133">Substitua "username@contoso.com" pela informação do usuário que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="967f8-133">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

<span data-ttu-id="967f8-134">O formato da URL especificado para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL para o pool de onde o serviço de migração hospedado estiver em execução, no seguinte formato: _Https://\<FQDN do Pool\>/HostedMigration/ hostedmigrationService.svc_.</span><span class="sxs-lookup"><span data-stu-id="967f8-134">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>
  
<span data-ttu-id="967f8-135">Você pode determinar a URL para o serviço de migração hospedado, exibindo a URL para o Skype para centro de administração de on-line de negócios para sua conta de locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="967f8-135">You can determine the URL to the Hosted Migration Service by viewing the URL for the Skype for Business Online Admin center for your Office 365 tenant account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="967f8-136">A URL é sensível a letras maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="967f8-136">The URL is case sensitive.</span></span> 
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="967f8-137">Para identificar a URL do Serviço de Migração Hospedada do seu locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="967f8-137">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="967f8-138">Faça logon no seu inquilino do Office 365 como um administrador.</span><span class="sxs-lookup"><span data-stu-id="967f8-138">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="967f8-139">Abra o **Centro de administração do Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="967f8-139">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="967f8-140">Com o **Centro de administração do Skype for Business** exibido, selecione e copie a URL na barra de endereço no **lync.com**. Uma URL de exemplo seria parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="967f8-140">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="967f8-141">Substitua **webdir** na URL por **admin**, o que resulta no seguinte:</span><span class="sxs-lookup"><span data-stu-id="967f8-141">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="967f8-142">Anexe a cadeia de caracteres a seguir à URL: **/HostedMigration/hostedmigrationService.svc**.</span><span class="sxs-lookup"><span data-stu-id="967f8-142">Append the following string to the URL: **/HostedMigration/hostedmigrationService.svc**.</span></span>
    
    <span data-ttu-id="967f8-143">A URL resultante, que é o valor do **HostedMigrationOverrideUrl**, deve se parecer com o seguinte:</span><span class="sxs-lookup"><span data-stu-id="967f8-143">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    

