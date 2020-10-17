---
title: 'Lync Server 2013: integrando o Lync Server e o Outlook Web App 2013'
description: 'Lync Server 2013: integrando o Lync Server e o Outlook Web App 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d9c7e91dba22f78325eaddc5b5d7469ccf4cc92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567387"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a><span data-ttu-id="73f41-103">Integrando o Microsoft Lync Server 2013 e o Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="73f41-103">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73f41-104">_**Última modificação do tópico:** 2013-02-03_</span><span class="sxs-lookup"><span data-stu-id="73f41-104">_**Topic Last Modified:** 2013-02-03_</span></span>

<span data-ttu-id="73f41-105">Além da integração com o Microsoft Outlook 2013, o Microsoft Lync Server 2013 pode ser totalmente integrado ao Microsoft Outlook Web App 2013; entre outras coisas, isso adiciona mensagens instantâneas e presença ao Outlook Web App e permite que sua lista de contatos unificado seja compartilhada entre o Outlook Web App e o Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="73f41-105">In addition to integrating with Microsoft Outlook 2013, Microsoft Lync Server 2013 can be fully integrated with Microsoft Outlook Web App 2013; among other things, this adds instant messaging and presence to Outlook Web App, and enables your unified contact list to be shared between Outlook Web App and Microsoft Lync 2013.</span></span> <span data-ttu-id="73f41-106">Para integrar o Lync Server 2013 e o Outlook Web App, você deve primeiro verificar se o tempo de execução da API gerenciada de comunicações unificadas 4,0 foi instalado no servidor back-end do Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="73f41-106">In order to integrate Lync Server 2013 and Outlook Web App, you must first verify that the Unified Communications Managed API 4.0 Runtime has been installed in your Microsoft Exchange Server 2013 backend server.</span></span> <span data-ttu-id="73f41-107">Você pode fazer isso verificando a existência do seguinte valor de registro:</span><span class="sxs-lookup"><span data-stu-id="73f41-107">You can do this by looking for the existence of the following registry value:</span></span>

<span data-ttu-id="73f41-108">HKEY \_ local \_ Machine \\ System \\ CurrentControlSet \\ Services \\ MSExchange OWA \\ instantmessaging \\ ImplementationDLLPath</span><span class="sxs-lookup"><span data-stu-id="73f41-108">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span></span>

<span data-ttu-id="73f41-109">O ImplementationDLLPath deve apontar para o local da pasta para o arquivo Microsoft.Rtc.Internal.Ucweb.dll.</span><span class="sxs-lookup"><span data-stu-id="73f41-109">The ImplementationDLLPath should point to the folder location for the file Microsoft.Rtc.Internal.Ucweb.dll.</span></span> <span data-ttu-id="73f41-110">Caso contrário, ou se o valor do registro não existir, você deverá baixar e instalar o programa de instalação do UCMA Runtime do centro de download da Microsoft em <https://www.microsoft.com/download/details.aspx?id=34992> .</span><span class="sxs-lookup"><span data-stu-id="73f41-110">If it does not, or if the registry value does not exist, then you should download and install the UCMA Runtime setup program from the Microsoft Download Center at <https://www.microsoft.com/download/details.aspx?id=34992>.</span></span> <span data-ttu-id="73f41-111">As informações sobre como instalar o tempo de execução do UCMA podem ser encontradas na mesma página da Web.</span><span class="sxs-lookup"><span data-stu-id="73f41-111">Information on how to install the UCMA Runtime can be found on that same web page.</span></span>

<span data-ttu-id="73f41-112">**Compatibilidade com versões anteriores**</span><span class="sxs-lookup"><span data-stu-id="73f41-112">**Backward Compatibility**</span></span>

<span data-ttu-id="73f41-113">O Lync Server 2013 pode ser integrado com as versões do Microsoft Exchange Server 2010 da Unificação de mensagens e do Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="73f41-113">Lync Server 2013 can be integrated with the Microsoft Exchange Server 2010 versions of both unified messaging and Outlook Web App.</span></span> <span data-ttu-id="73f41-114">Para obter mais informações, consulte o artigo Deploying on-premises Exchange UM para fornecer mensagens de voz do Lync Server 2010 em [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) .</span><span class="sxs-lookup"><span data-stu-id="73f41-114">For more information, see the article Deploying On-Premises Exchange UM to Provide Lync Server 2010 Voice Mail at [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md).</span></span> <span data-ttu-id="73f41-115">Se você integrar com o Exchange 2010, não terá recursos específicos do Lync Server, como o repositório unificado de contatos e o arquivamento do Lync para Exchange.</span><span class="sxs-lookup"><span data-stu-id="73f41-115">If you integrate with Exchange 2010 you will not have Lync Server specific features such as the unified contact store and Lync-to-Exchange archiving.</span></span>

<span data-ttu-id="73f41-116">O Microsoft Lync 2013 também pode ser usado em conjunto com o Exchange 2010 e o Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="73f41-116">Microsoft Lync 2013 can also be used in conjunction with Exchange 2010 and Outlook 2010.</span></span> <span data-ttu-id="73f41-117">Novamente, no entanto, novas funcionalidades, como o repositório unificado de contatos e fotos de alta resolução, não estarão disponíveis para os usuários do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="73f41-117">Once again, however, new functionality such as the unified contact store and high-resolution photos will not be available to Lync 2013 users.</span></span> <span data-ttu-id="73f41-118">Esses novos recursos exigem o Lync Server 2013 e o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="73f41-118">These new capabilities require both Lync Server 2013 and Exchange 2013.</span></span>

<span data-ttu-id="73f41-119">**Criando um pool de aplicativos confiáveis para o Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="73f41-119">**Creating a Trusted Application Pool for Outlook Web App**</span></span>

<span data-ttu-id="73f41-120">Se você instalou o serviço de roteador de chamadas de Unificação de mensagens do Microsoft Exchange e o serviço de Unificação de mensagens do Microsoft Exchange no mesmo computador, não há necessidade de criar um pool de aplicativos confiáveis para o Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="73f41-120">If you have installed the Microsoft Exchange Unified Messaging Call Router service and the Microsoft Exchange Unified Messaging service on the same computer then there is no need to create a trusted application pool for Outlook Web App.</span></span> <span data-ttu-id="73f41-121">(Isso pressupõe que o servidor em questão esteja hospedando um plano de discagem da UM do SipName.) Se você estiver usando um único computador para hospedar esses serviços, poderá pular para a seção deste documento com a **habilitação de mensagens instantâneas no Outlook Web App**.</span><span class="sxs-lookup"><span data-stu-id="73f41-121">(This assumes that the server in question is hosting a SipName UM dial plan.) If you are using a single computer to host both of these services then you can skip to the section of this document titled **Enabling Instant Messaging on Outlook Web App**.</span></span>

<span data-ttu-id="73f41-122">O Lync Server 2013 pode descobrir a descoberta automática de qualquer servidor do Exchange que hospede um plano de discagem da UM do SipName; Esses servidores são automaticamente adicionados à lista de servidores conhecidos do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73f41-122">Lync Server 2013 can autodiscover any Exchange servers that host a SipName UM dial plan; these servers are automatically added to the Lync Server Known Servers List.</span></span> <span data-ttu-id="73f41-123">Não é necessário criar um pool de aplicativos confiáveis e adicionar esses servidores à lista de servidores conhecidos.</span><span class="sxs-lookup"><span data-stu-id="73f41-123">There is no need to create a trusted application pool and add these servers to the Known Servers List.</span></span> <span data-ttu-id="73f41-124">Na verdade, fazer isso fará com que a integração do Outlook Web App pare de funcionar.</span><span class="sxs-lookup"><span data-stu-id="73f41-124">In fact, doing so will cause Outlook Web App integration to stop working.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73f41-125">Isso se deve ao fato de que a topologia do Lync Server agora terá duas entradas para o mesmo computador: a entrada descoberta automática e a entrada adicionada manualmente.</span><span class="sxs-lookup"><span data-stu-id="73f41-125">This is due to the fact that the Lync Server topology will now have two entries for the same computer: the autodiscovered entry, and the manually-added entry.</span></span> <span data-ttu-id="73f41-126">Para corrigir o problema e para fazer com que o Outlook Web App funcione novamente, use o Windows PowerShell para remover as entradas de pool confiável e de aplicativo confiável para o servidor.</span><span class="sxs-lookup"><span data-stu-id="73f41-126">To fix the problem, and to get Outlook Web App working again, use Windows PowerShell to remove the trusted pool and trusted application entries for the server.</span></span> <span data-ttu-id="73f41-127">Consulte os tópicos de ajuda para os cmdlets <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="73f41-127">See the help topics for the <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> cmdlets for more information.</span></span>



</div>

<span data-ttu-id="73f41-128">Se esses dois serviços estiverem em execução em computadores separados, depois que você tiver verificado que o tempo de execução do Unified Communications Managed API 4,0 foi instalado, você deve criar um pool de aplicativos confiável do Lync Server e um aplicativo confiável associado ao Outlook Web App; Isso adicionará o servidor à lista de servidores conhecidos.</span><span class="sxs-lookup"><span data-stu-id="73f41-128">If these two services are running on separate computers then, after you have verified that the Unified Communications Managed API 4.0 Runtime has been installed, you must create a Lync Server trusted application pool and a trusted application associated with Outlook Web App; that will add the server to the Known Servers List.</span></span> <span data-ttu-id="73f41-129">Para fazer isso, primeiro execute um comando semelhante a este no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="73f41-129">To do that, first run a command similar to this from within the Lync Server Management Shell:</span></span>

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

<span data-ttu-id="73f41-130">No comando anterior, atl-owa-001.litwareinc.com é o nome de domínio totalmente qualificado do pool do Outlook Web App; Este deve ser o mesmo nome que aparece nos campos nome alternativo do assunto e nome da entidade (SAN) do certificado que fornece acesso ao Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="73f41-130">In the preceding command, atl-owa-001.litwareinc.com is the fully qualified domain name of the Outlook Web App pool; this must be the same name that appears in the Subject Name and Subject Alternative Name (SAN) fields of the certificate that provides access to Outlook Web App.</span></span> <span data-ttu-id="73f41-131">Da mesma forma, atl-cs-001.litwareinc.com é o nome de domínio totalmente qualificado do pool do Lync Server 2013 que hospedará o novo pool de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="73f41-131">Likewise, atl-cs-001.litwareinc.com is the fully qualified domain name of the Lync Server 2013 pool that will host the new trusted application pool.</span></span> <span data-ttu-id="73f41-132">Observe também que o site especificado, Redmond, representa o SiteId do site do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73f41-132">Note, too that the specified site, Redmond, represents the SiteID of the Lync Server site.</span></span> <span data-ttu-id="73f41-133">O SiteId não é necessariamente o mesmo que o DisplayName do site; Você pode recuperar o SiteIDs para seus sites do Lync Server executando o seguinte comando no Shell de gerenciamento do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="73f41-133">The SiteID is not necessarily the same as the site's DisplayName; you can retrieve SiteIDs for your Lync Server sites by running the following command from the Lync Server Management Shell:</span></span>

    Get-CsSite | Select-Object DisplayName, SiteID

<span data-ttu-id="73f41-134">Depois de criar o pool de aplicativos confiáveis, use um comando semelhante ao seguinte para configurar uma identidade de aplicativo e uma porta para o Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="73f41-134">After creating the trusted application pool, use a command similar to the following to configure an application Identity and a port for Outlook Web App:</span></span>

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

<span data-ttu-id="73f41-p110">No comando anterior, o ApplicationID é simplesmente um identificador amigável usado para distinguir aplicativos confiáveis. O ApplicationID pode ser qualquer cadeia de caracteres de texto que não inclua espaços em branco ou outros caracteres proibidos. (Para garantir que você criará um identificador válido, é recomendado que apenas letras e números sejam utilizados ao especificar um ApplicationId.) O valor atribuído ao parâmetro Porta também é deixado ao critério do administrador: ela pode ser qualquer porta de rede disponível.</span><span class="sxs-lookup"><span data-stu-id="73f41-p110">In the preceding command, the ApplicationID is simply a friendly identifier used to distinguish trusted applications. The ApplicationID can be any text string that does not include blank spaces or other prohibited characters. (To ensure that you create a valid identifier, it is recommended that you use only letters and numbers when specifying an ApplicationId.) The value assigned to the Port parameter is also left to the administrator's discretion: this can be any available network port.</span></span>

<span data-ttu-id="73f41-138">Após criar o aplicativo confiável, você deve executar o seguinte comando para habilitar as alterações na sua topologia do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="73f41-138">After creating the trusted application you must run the following command to enable the changes to your Lync Server topology:</span></span>

    Enable-CsTopology

<span data-ttu-id="73f41-139">Observe que você também deve adicionar o servidor de caixa de correio e acesso para cliente do Exchange a todos os planos de discagem URI do SIP.</span><span class="sxs-lookup"><span data-stu-id="73f41-139">Note that you must also add your Exchange client access and mailbox server to all of your SIP Uri dial plans.</span></span> <span data-ttu-id="73f41-140">Por sua vez, isso configurará os servidores como Peers SIP confiáveis com a topologia ExUmRouting para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73f41-140">In turn, this will configure the servers as trusted SIP peers with the ExUmRouting topology for Lync Server.</span></span>

<span data-ttu-id="73f41-141">**Habilitando o sistema de mensagens instantâneas no Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="73f41-141">**Enabling Instant Messaging on Outlook Web App**</span></span>

<span data-ttu-id="73f41-142">Com o Lync Server configurado corretamente, você pode começar a configurar o Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="73f41-142">With Lync Server correctly configured you can then begin to configure Outlook Web App.</span></span> <span data-ttu-id="73f41-143">A primeira etapa desse processo é habilitar o sistema de mensagens instantâneas em todos os diretórios virtuais do Outlook Web App em seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="73f41-143">The first step in that process is to enable instant messaging on all your Outlook Web App virtual directories on your front end servers.</span></span> <span data-ttu-id="73f41-144">(Não é necessário habilitar o sistema de mensagens instantâneas para os diretórios virtuais em seus servidores de back-end.</span><span class="sxs-lookup"><span data-stu-id="73f41-144">(There is no need to enable instant messaging for the virtual directories on your backend servers.</span></span> <span data-ttu-id="73f41-145">Na verdade, é recomendável não habilitar o sistema de mensagens instantâneas em seus servidores de back-end. As mensagens instantâneas podem ser habilitadas nos servidores de acesso para cliente executando o seguinte comando no Shell de gerenciamento do Exchange:</span><span class="sxs-lookup"><span data-stu-id="73f41-145">In fact, it is recommended that you do not enable instant messaging on your backend servers.) Instant messaging can be enabled on the client access servers by running the following command from within the Exchange Management Shell:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> <span data-ttu-id="73f41-146">Por padrão, o sistema de mensagens instantâneas é habilitado quando você instala o Outlook Web App; ou seja, a propriedade InstantMessagingEnabled é definida como true.</span><span class="sxs-lookup"><span data-stu-id="73f41-146">By default, instant messaging is enabled when you install Outlook Web App; that is, the InstantMessagingEnabled property is set to True.</span></span> <span data-ttu-id="73f41-147">No entanto, você ainda deve executar o comando anterior para definir o tipo de sistema de mensagens instantâneas como o OCS.</span><span class="sxs-lookup"><span data-stu-id="73f41-147">However, you must still run the preceding command in order to set the instant messaging type to OCS.</span></span> <span data-ttu-id="73f41-148">Por padrão, InstantMessagingType é definido como nenhum.</span><span class="sxs-lookup"><span data-stu-id="73f41-148">By default, InstantMessagingType is set to None.</span></span>



</div>

<span data-ttu-id="73f41-149">Em seguida, você deve adicionar as duas linhas a seguir ao arquivo de Web.config do Outlook Web App (esse arquivo é normalmente localizado na pasta C: \\ arquivos de programas \\ Microsoft \\ Exchange Server \\ v15 \\ ClientAccess \\ OWA).</span><span class="sxs-lookup"><span data-stu-id="73f41-149">Next you must add the following two lines to Outlook Web App Web.config file (this file is typically located in the folder C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa).</span></span> <span data-ttu-id="73f41-150">Essas duas linhas devem ser adicionadas sob o \<AppSettings\> nó no arquivo Web.config e este procedimento deve ser executado apenas nos servidores de back-end em que o Outlook Web App foi instalado:</span><span class="sxs-lookup"><span data-stu-id="73f41-150">These two lines should be added under the \<AppSettings\> node in the Web.config file, and this procedure should be carried out only on the backend servers where Outlook Web App has been installed:</span></span>

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

<span data-ttu-id="73f41-151">No exemplo anterior, o valor de IMCertificateThumbprint deve ser a impressão digital para o certificado do Exchange 2013 que é instalado nos seus servidores de back-end.</span><span class="sxs-lookup"><span data-stu-id="73f41-151">In the preceding example, the value for IMCertificateThumbprint must be the thumbprint for the Exchange 2013 certificate that is installed on your backend servers.</span></span> <span data-ttu-id="73f41-152">Você pode recuperar essas informações executando o seguinte comando no Shell de gerenciamento do Exchange:</span><span class="sxs-lookup"><span data-stu-id="73f41-152">You can retrieve that information by running the following command from the Exchange Management Shell:</span></span>

    Get-ExchangeCertificate

<span data-ttu-id="73f41-153">Observe também que o valor atribuído ao imservername é o nome de domínio totalmente qualificado do pool do Lync Server no qual você criou o pool de aplicativos confiáveis para o Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="73f41-153">Note, too that the value assigned to IMServerName is the fully qualified domain name of the Lync Server pool where you created the trusted application pool for Outlook Web App.</span></span>

<span data-ttu-id="73f41-154">O certificado que você usa para o Outlook Web App deve ser um certificado confiável para o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73f41-154">The certificate that you use for Outlook Web App must be a certificate that is trusted by Lync Server.</span></span> <span data-ttu-id="73f41-155">Uma maneira de garantir que o certificado seja confiável pelo Lync Server e o Exchange é usar sua autoridade de certificação interna para criar um certificado no servidor de caixa de correio, certificando-se de que o FQDN do servidor é usado para o nome da entidade e que esse FQDN aparece no campo nome alternativo do certificado.</span><span class="sxs-lookup"><span data-stu-id="73f41-155">One way to ensure that the certificate will be trusted by both Lync Server and Exchange is to use your internal certificate authority to create a certificate on the mailbox server, making sure that the server FQDN is used for the subject name and that this FQDN appears in the certificate alternate name field.</span></span> <span data-ttu-id="73f41-156">Após o certificado ter sido criado, ele pode ser importado para seus servidores de back-end.</span><span class="sxs-lookup"><span data-stu-id="73f41-156">After the certificate has been created it can then be imported to your backend servers.</span></span> <span data-ttu-id="73f41-157">O resultado líquido é que o mesmo certificado é usado para duas finalidades: 1) comunicação entre a Unificação de mensagens do Exchange e o Lync Server; e 2) a integração entre o Outlook Web App e o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73f41-157">The net result is that the same certificate is used for two purposes: 1) communication between Exchange unified messaging and Lync Server; and, 2) the integration between Outlook Web App and Lync Server.</span></span>

<span data-ttu-id="73f41-158">Depois de atualizar o arquivo de Web.config, você deve executar o seguinte comando no servidor back-end do Exchange para reciclar o pool do Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="73f41-158">After you have updated the Web.config file you should then run the following command on the Exchange backend server in order to recycle the Outlook Web App pool:</span></span>

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

<span data-ttu-id="73f41-159">Se a operação de reciclagem for bem sucedida, você verá a seguinte mensagem no Shell de gerenciamento do Exchange:</span><span class="sxs-lookup"><span data-stu-id="73f41-159">If the recycle operation succeeds you will see the following message in the Exchange Management Shell:</span></span>

    "MSExchangeOWAAppPool" successfully recycled

<span data-ttu-id="73f41-160">**Configurando políticas de caixa de correio do Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="73f41-160">**Configuring Outlook Web App Mailbox Policies**</span></span>

<span data-ttu-id="73f41-161">Neste ponto, você pode usar o seguinte comando para configurar o sistema de mensagens instantâneas na política de caixa de correio (ou políticas) apropriada do Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="73f41-161">At this point you can use the following command to configure instant messaging on the appropriate Outlook Web App mailbox policy (or policies).</span></span> <span data-ttu-id="73f41-162">Por exemplo, este comando, executado em um de seus servidores de caixa de correio, permite mensagens instantâneas na política padrão:</span><span class="sxs-lookup"><span data-stu-id="73f41-162">For example, this command, run on one of your mailbox servers, enables instant messaging on the Default policy:</span></span>

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="73f41-163">E este comando habilita o sistema de mensagens instantâneas para todas as suas políticas de caixa de correio do Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="73f41-163">And this command enables instant messaging for all your Outlook Web App mailbox policies:</span></span>

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="73f41-164">Depois que a política de caixa de correio for habilitada, todos os usuários gerenciados por essa política terão integração total entre o Lync Server e o Outlook Web App, desde que:</span><span class="sxs-lookup"><span data-stu-id="73f41-164">After the mailbox policy has been enabled then all users managed by that policy will have full integration between Lync Server and Outlook Web App, provided that:</span></span>

  - <span data-ttu-id="73f41-165">O usuário tem uma caixa de correio no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="73f41-165">The user has a mailbox on Exchange 2013.</span></span>

  - <span data-ttu-id="73f41-166">O usuário foi habilitado para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="73f41-166">The user has been enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="73f41-167">O usuário possui um endereço de proxy SIP válido.</span><span class="sxs-lookup"><span data-stu-id="73f41-167">The user has a valid SIP proxy address.</span></span>

<span data-ttu-id="73f41-168">**Desabilitando o sistema de mensagens instantâneas no Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="73f41-168">**Disabling Instant Messaging in Outlook Web App**</span></span>

<span data-ttu-id="73f41-169">Conforme observado anteriormente, as mensagens instantâneas são habilitadas por padrão no Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="73f41-169">As noted previously, instant messaging is enabled by default in Outlook Web App.</span></span> <span data-ttu-id="73f41-170">Isso significa que, se você não integrar o Outlook Web App com o Lync Server, os usuários verão ícones de presença em branco e uma mensagem de erro sempre que fizerem logon no Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="73f41-170">That means that, if you do not integrate Outlook Web App with Lync Server, users will see blank presence icons and an error message each time they log on to Outlook Web App.</span></span> <span data-ttu-id="73f41-171">Para evitar esse problema, use o seguinte comando do Shell de gerenciamento do Exchange para desabilitar o sistema de mensagens instantâneas no Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="73f41-171">To prevent this problem, use the following Exchange Management Shell command to disable instant messaging in Outlook web App:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

<span data-ttu-id="73f41-172">**Verificando a integração com o Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="73f41-172">**Verifying Integration With Outlook Web App**</span></span>

<span data-ttu-id="73f41-173">Para verificar se as mensagens instantâneas e a presença foram integradas ao Outlook Web App, entre no Outlook Web App 2013.</span><span class="sxs-lookup"><span data-stu-id="73f41-173">To verify that instant messaging and presence have been integrated with Outlook Web App, sign on to Outlook Web App 2013.</span></span> <span data-ttu-id="73f41-174">No canto superior direito da tela, você verá o seu nome para exibição do Exchange.</span><span class="sxs-lookup"><span data-stu-id="73f41-174">In the upper right-hand corner of the screen, you will see your Exchange display name.</span></span> <span data-ttu-id="73f41-175">Se houver um ícone de presença ao lado do seu nome (por exemplo, um ícone verde indicando que o status atual está disponível) indica que você integrou com êxito o Lync Server e o Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="73f41-175">If there is a presence icon next to your name (for example, a green icon indicating that your current status is Available) that indicates that you have successfully integrated Lync Server and Outlook Web App.</span></span>

<span data-ttu-id="73f41-176">Após o logon inicial no Outlook Web App, verifique se um evento com a identificação de evento 112 (e o MSExchange OWA de origem) foi gravado no log de eventos no servidor de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="73f41-176">After the initial sign-on to Outlook Web App, check to see if an event with the Event ID 112 (and the source MSExchange OWA) has been written to the event log on the mailbox server.</span></span> <span data-ttu-id="73f41-177">Esse evento indica que o Gerenciador de ponto de extremidade de mensagens instantâneas foi inicializado com êxito.</span><span class="sxs-lookup"><span data-stu-id="73f41-177">This event indicates that the Instant Messaging Endpoint Manager was successfully initialized.</span></span> <span data-ttu-id="73f41-178">Se as mensagens instantâneas não parecerem estar funcionando, no servidor de caixa de correio, procure arquivos de log na pasta C: \\ arquivos de programa \\ Microsoft \\ Exchange Server \\ v15 \\ Logging \\ owa \\ instantmessaging.</span><span class="sxs-lookup"><span data-stu-id="73f41-178">If instant messaging does not appear to be working then, on the mailbox server, look for log files in the folder C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging.</span></span> <span data-ttu-id="73f41-179">Se o registro em log ou as pastas InstantMessaging não existirem, indica que a integração falhou.</span><span class="sxs-lookup"><span data-stu-id="73f41-179">If either the Logging or the InstantMessaging folders do not exist that indicates that integration has failed.</span></span> <span data-ttu-id="73f41-180">Nesse caso, você pode usar o rastreamento do SIPStack no Lync Server (todos os níveis e todos os sinalizadores) para tentar determinar por que a integração falhou.</span><span class="sxs-lookup"><span data-stu-id="73f41-180">In that case, you can use SIPStack tracing on Lync Server (All Levels and All Flags) to try and determine why integration failed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

