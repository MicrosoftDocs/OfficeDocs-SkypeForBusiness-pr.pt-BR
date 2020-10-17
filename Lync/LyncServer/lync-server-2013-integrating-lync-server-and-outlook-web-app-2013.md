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
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>Integrando o Microsoft Lync Server 2013 e o Microsoft Outlook Web App 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-03_

Além da integração com o Microsoft Outlook 2013, o Microsoft Lync Server 2013 pode ser totalmente integrado ao Microsoft Outlook Web App 2013; entre outras coisas, isso adiciona mensagens instantâneas e presença ao Outlook Web App e permite que sua lista de contatos unificado seja compartilhada entre o Outlook Web App e o Microsoft Lync 2013. Para integrar o Lync Server 2013 e o Outlook Web App, você deve primeiro verificar se o tempo de execução da API gerenciada de comunicações unificadas 4,0 foi instalado no servidor back-end do Microsoft Exchange Server 2013. Você pode fazer isso verificando a existência do seguinte valor de registro:

HKEY \_ local \_ Machine \\ System \\ CurrentControlSet \\ Services \\ MSExchange OWA \\ instantmessaging \\ ImplementationDLLPath

O ImplementationDLLPath deve apontar para o local da pasta para o arquivo Microsoft.Rtc.Internal.Ucweb.dll. Caso contrário, ou se o valor do registro não existir, você deverá baixar e instalar o programa de instalação do UCMA Runtime do centro de download da Microsoft em <https://www.microsoft.com/download/details.aspx?id=34992> . As informações sobre como instalar o tempo de execução do UCMA podem ser encontradas na mesma página da Web.

**Compatibilidade com versões anteriores**

O Lync Server 2013 pode ser integrado com as versões do Microsoft Exchange Server 2010 da Unificação de mensagens e do Outlook Web App. Para obter mais informações, consulte o artigo Deploying on-premises Exchange UM para fornecer mensagens de voz do Lync Server 2010 em [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) . Se você integrar com o Exchange 2010, não terá recursos específicos do Lync Server, como o repositório unificado de contatos e o arquivamento do Lync para Exchange.

O Microsoft Lync 2013 também pode ser usado em conjunto com o Exchange 2010 e o Outlook 2010. Novamente, no entanto, novas funcionalidades, como o repositório unificado de contatos e fotos de alta resolução, não estarão disponíveis para os usuários do Lync 2013. Esses novos recursos exigem o Lync Server 2013 e o Exchange 2013.

**Criando um pool de aplicativos confiáveis para o Outlook Web App**

Se você instalou o serviço de roteador de chamadas de Unificação de mensagens do Microsoft Exchange e o serviço de Unificação de mensagens do Microsoft Exchange no mesmo computador, não há necessidade de criar um pool de aplicativos confiáveis para o Outlook Web App. (Isso pressupõe que o servidor em questão esteja hospedando um plano de discagem da UM do SipName.) Se você estiver usando um único computador para hospedar esses serviços, poderá pular para a seção deste documento com a **habilitação de mensagens instantâneas no Outlook Web App**.

O Lync Server 2013 pode descobrir a descoberta automática de qualquer servidor do Exchange que hospede um plano de discagem da UM do SipName; Esses servidores são automaticamente adicionados à lista de servidores conhecidos do Lync Server. Não é necessário criar um pool de aplicativos confiáveis e adicionar esses servidores à lista de servidores conhecidos. Na verdade, fazer isso fará com que a integração do Outlook Web App pare de funcionar.

<div>


> [!NOTE]  
> Isso se deve ao fato de que a topologia do Lync Server agora terá duas entradas para o mesmo computador: a entrada descoberta automática e a entrada adicionada manualmente. Para corrigir o problema e para fazer com que o Outlook Web App funcione novamente, use o Windows PowerShell para remover as entradas de pool confiável e de aplicativo confiável para o servidor. Consulte os tópicos de ajuda para os cmdlets <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> para obter mais informações.



</div>

Se esses dois serviços estiverem em execução em computadores separados, depois que você tiver verificado que o tempo de execução do Unified Communications Managed API 4,0 foi instalado, você deve criar um pool de aplicativos confiável do Lync Server e um aplicativo confiável associado ao Outlook Web App; Isso adicionará o servidor à lista de servidores conhecidos. Para fazer isso, primeiro execute um comando semelhante a este no Shell de gerenciamento do Lync Server:

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

No comando anterior, atl-owa-001.litwareinc.com é o nome de domínio totalmente qualificado do pool do Outlook Web App; Este deve ser o mesmo nome que aparece nos campos nome alternativo do assunto e nome da entidade (SAN) do certificado que fornece acesso ao Outlook Web App. Da mesma forma, atl-cs-001.litwareinc.com é o nome de domínio totalmente qualificado do pool do Lync Server 2013 que hospedará o novo pool de aplicativos confiáveis. Observe também que o site especificado, Redmond, representa o SiteId do site do Lync Server. O SiteId não é necessariamente o mesmo que o DisplayName do site; Você pode recuperar o SiteIDs para seus sites do Lync Server executando o seguinte comando no Shell de gerenciamento do Lync Server:

    Get-CsSite | Select-Object DisplayName, SiteID

Depois de criar o pool de aplicativos confiáveis, use um comando semelhante ao seguinte para configurar uma identidade de aplicativo e uma porta para o Outlook Web App:

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

No comando anterior, o ApplicationID é simplesmente um identificador amigável usado para distinguir aplicativos confiáveis. O ApplicationID pode ser qualquer cadeia de caracteres de texto que não inclua espaços em branco ou outros caracteres proibidos. (Para garantir que você criará um identificador válido, é recomendado que apenas letras e números sejam utilizados ao especificar um ApplicationId.) O valor atribuído ao parâmetro Porta também é deixado ao critério do administrador: ela pode ser qualquer porta de rede disponível.

Após criar o aplicativo confiável, você deve executar o seguinte comando para habilitar as alterações na sua topologia do Lync Server:

    Enable-CsTopology

Observe que você também deve adicionar o servidor de caixa de correio e acesso para cliente do Exchange a todos os planos de discagem URI do SIP. Por sua vez, isso configurará os servidores como Peers SIP confiáveis com a topologia ExUmRouting para o Lync Server.

**Habilitando o sistema de mensagens instantâneas no Outlook Web App**

Com o Lync Server configurado corretamente, você pode começar a configurar o Outlook Web App. A primeira etapa desse processo é habilitar o sistema de mensagens instantâneas em todos os diretórios virtuais do Outlook Web App em seus servidores front-end. (Não é necessário habilitar o sistema de mensagens instantâneas para os diretórios virtuais em seus servidores de back-end. Na verdade, é recomendável não habilitar o sistema de mensagens instantâneas em seus servidores de back-end. As mensagens instantâneas podem ser habilitadas nos servidores de acesso para cliente executando o seguinte comando no Shell de gerenciamento do Exchange:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> Por padrão, o sistema de mensagens instantâneas é habilitado quando você instala o Outlook Web App; ou seja, a propriedade InstantMessagingEnabled é definida como true. No entanto, você ainda deve executar o comando anterior para definir o tipo de sistema de mensagens instantâneas como o OCS. Por padrão, InstantMessagingType é definido como nenhum.



</div>

Em seguida, você deve adicionar as duas linhas a seguir ao arquivo de Web.config do Outlook Web App (esse arquivo é normalmente localizado na pasta C: \\ arquivos de programas \\ Microsoft \\ Exchange Server \\ v15 \\ ClientAccess \\ OWA). Essas duas linhas devem ser adicionadas sob o \<AppSettings\> nó no arquivo Web.config e este procedimento deve ser executado apenas nos servidores de back-end em que o Outlook Web App foi instalado:

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

No exemplo anterior, o valor de IMCertificateThumbprint deve ser a impressão digital para o certificado do Exchange 2013 que é instalado nos seus servidores de back-end. Você pode recuperar essas informações executando o seguinte comando no Shell de gerenciamento do Exchange:

    Get-ExchangeCertificate

Observe também que o valor atribuído ao imservername é o nome de domínio totalmente qualificado do pool do Lync Server no qual você criou o pool de aplicativos confiáveis para o Outlook Web App.

O certificado que você usa para o Outlook Web App deve ser um certificado confiável para o Lync Server. Uma maneira de garantir que o certificado seja confiável pelo Lync Server e o Exchange é usar sua autoridade de certificação interna para criar um certificado no servidor de caixa de correio, certificando-se de que o FQDN do servidor é usado para o nome da entidade e que esse FQDN aparece no campo nome alternativo do certificado. Após o certificado ter sido criado, ele pode ser importado para seus servidores de back-end. O resultado líquido é que o mesmo certificado é usado para duas finalidades: 1) comunicação entre a Unificação de mensagens do Exchange e o Lync Server; e 2) a integração entre o Outlook Web App e o Lync Server.

Depois de atualizar o arquivo de Web.config, você deve executar o seguinte comando no servidor back-end do Exchange para reciclar o pool do Outlook Web App:

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

Se a operação de reciclagem for bem sucedida, você verá a seguinte mensagem no Shell de gerenciamento do Exchange:

    "MSExchangeOWAAppPool" successfully recycled

**Configurando políticas de caixa de correio do Outlook Web App**

Neste ponto, você pode usar o seguinte comando para configurar o sistema de mensagens instantâneas na política de caixa de correio (ou políticas) apropriada do Outlook Web App. Por exemplo, este comando, executado em um de seus servidores de caixa de correio, permite mensagens instantâneas na política padrão:

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

E este comando habilita o sistema de mensagens instantâneas para todas as suas políticas de caixa de correio do Outlook Web App:

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Depois que a política de caixa de correio for habilitada, todos os usuários gerenciados por essa política terão integração total entre o Lync Server e o Outlook Web App, desde que:

  - O usuário tem uma caixa de correio no Exchange 2013.

  - O usuário foi habilitado para o Lync Server 2013.

  - O usuário possui um endereço de proxy SIP válido.

**Desabilitando o sistema de mensagens instantâneas no Outlook Web App**

Conforme observado anteriormente, as mensagens instantâneas são habilitadas por padrão no Outlook Web App. Isso significa que, se você não integrar o Outlook Web App com o Lync Server, os usuários verão ícones de presença em branco e uma mensagem de erro sempre que fizerem logon no Outlook Web App. Para evitar esse problema, use o seguinte comando do Shell de gerenciamento do Exchange para desabilitar o sistema de mensagens instantâneas no Outlook Web App:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Verificando a integração com o Outlook Web App**

Para verificar se as mensagens instantâneas e a presença foram integradas ao Outlook Web App, entre no Outlook Web App 2013. No canto superior direito da tela, você verá o seu nome para exibição do Exchange. Se houver um ícone de presença ao lado do seu nome (por exemplo, um ícone verde indicando que o status atual está disponível) indica que você integrou com êxito o Lync Server e o Outlook Web App.

Após o logon inicial no Outlook Web App, verifique se um evento com a identificação de evento 112 (e o MSExchange OWA de origem) foi gravado no log de eventos no servidor de caixa de correio. Esse evento indica que o Gerenciador de ponto de extremidade de mensagens instantâneas foi inicializado com êxito. Se as mensagens instantâneas não parecerem estar funcionando, no servidor de caixa de correio, procure arquivos de log na pasta C: \\ arquivos de programa \\ Microsoft \\ Exchange Server \\ v15 \\ Logging \\ owa \\ instantmessaging. Se o registro em log ou as pastas InstantMessaging não existirem, indica que a integração falhou. Nesse caso, você pode usar o rastreamento do SIPStack no Lync Server (todos os níveis e todos os sinalizadores) para tentar determinar por que a integração falhou.

</div>

<span> </span>

</div>

</div>

</div>

