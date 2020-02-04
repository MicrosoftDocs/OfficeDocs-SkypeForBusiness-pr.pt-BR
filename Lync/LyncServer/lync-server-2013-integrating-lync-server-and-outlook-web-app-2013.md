---
title: 'Lync Server 2013: integrando o Lync Server e o Outlook Web App 2013'
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
ms.openlocfilehash: faa75694ecaac662a643d331a4efdf91b41223e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a>Integração do Microsoft Lync Server 2013 e do Microsoft Outlook Web App 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-03_

Além da integração com o Microsoft Outlook 2013, o Microsoft Lync Server 2013 pode ser totalmente integrado ao Microsoft Outlook Web App 2013; entre outras coisas, isso adiciona mensagem instantânea e presença ao Outlook Web App e permite que sua lista de contatos unificado seja compartilhada entre o Outlook Web App e o Microsoft Lync 2013. Para integrar o Lync Server 2013 e o Outlook Web App, primeiro você deve verificar se o tempo de execução da 4,0 API gerenciada de comunicação unificada foi instalado no servidor do Microsoft Exchange Server 2013 back-end. Você pode fazer isso verificando a existência do seguinte valor de registro:

HKEY\_local\_Machine\\System\\CurrentControlSet\\Services\\MSExchange OWA\\instantmessaging\\ImplementationDLLPath

O ImplementationDLLPath deve apontar para a localização da pasta do arquivo Microsoft.Rtc.Internal.Ucweb.dll. Se não houver, ou se o valor do registro não existir, você deverá baixar e instalar o programa de instalação do UCMA Runtime a partir do centro de download <http://www.microsoft.com/en-us/download/details.aspx?id=34992>da Microsoft em. As informações sobre como instalar o UCMA Runtime podem ser encontradas na mesma página da web.

**Retrocompatibilidade**

O Lync Server 2013 pode ser integrado ao Microsoft Exchange Server 2010 versões do Unificação de mensagens e do Outlook Web App. Para obter mais informações, consulte o artigo implantando o Exchange UM local para fornecer correio de voz do Lync [http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)Server 2010 em. Se você se integrar ao Exchange 2010, não terá recursos específicos do Lync Server, como o repositório de contatos unificado e o arquivamento de Lync para Exchange.

O Microsoft Lync 2013 também pode ser usado em conjunto com o Exchange 2010 e o Outlook 2010. Mais uma vez, no entanto, novas funcionalidades, como o repositório de contatos unificado e fotos de alta resolução, não estarão disponíveis para os usuários do Lync 2013. Esses novos recursos exigem o Lync Server 2013 e o Exchange 2013.

**Para criar um pool de aplicativos confiáveis para o Outlook Web App**

Se você tiver instalado o serviço de roteador de chamada de Unificação de mensagens do Microsoft Exchange e o serviço de Unificação de mensagens do Microsoft Exchange no mesmo computador, não há necessidade de criar um pool de aplicativos confiável para o Outlook Web App. (Isso pressupõe que o servidor em questão está hospedando um plano de discagem de UM SipName.) Se você estiver usando um único computador para hospedar esses dois serviços, pode pular para a seção deste documento intitulado ativando o recurso de **mensagens instantâneas no Outlook Web App**.

O Lync Server 2013 pode descobrir a descoberta automática de qualquer servidor Exchange que hospede um plano de discagem de um SipName; Esses servidores são adicionados automaticamente à lista de servidores conhecidos do Lync Server. Não é necessário criar um pool de aplicativos confiáveis e adicionar esses servidores à lista de servidores conhecidos. Na verdade, fazer isso pode até fazer com que a integração do Outlook Web App pare de funcionar.

<div>


> [!NOTE]  
> Isso se deve ao fato de que a topologia do Lync Server agora terá duas entradas para o mesmo computador: a entrada descoberta automática e a entrada manualmente adicionada. Para corrigir esse problema e fazer com que o Outlook Web App volte a funcionar, use o Windows PowerShell para remover as entradas de pool confiável e aplicativo confiável para o servidor. Consulte os tópicos de ajuda para os cmdlets <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> e <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> para obter mais informações.



</div>

Se esses dois serviços estiverem em execução em computadores separados, depois de verificar se o tempo de execução da API gerenciada de comunicação unificada 4,0 foi instalado, você deve criar um pool de aplicativos confiável do Lync Server e um aplicativo confiável associado ao Outlook Web App; Isso vai adicionar o servidor à lista de servidores conhecidos. Para fazer isso, primeiro execute um comando semelhante a isso dentro do Shell de gerenciamento do Lync Server:

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

No comando anterior, atl-owa-001.litwareinc.com é o nome de domínio totalmente qualificado do pool do Outlook Web App, ele deve ter o mesmo nome que é exibido nos campos Nome da Entidade e Nome Alternativo da Entidade (SAN) do certificado que fornece acesso ao Otlook Web App. Da mesma forma, atl-cs-001.litwareinc.com é o nome de domínio totalmente qualificado do pool do Lync Server 2013 que irá hospedar o novo pool de aplicativos confiáveis. Observe também que o site especificado, Redmond, representa o SiteId do site do Lync Server. O SiteId não é necessariamente o mesmo que o DisplayName do site; Você pode recuperar o SiteIDs para seus sites do Lync Server executando o seguinte comando no Shell de gerenciamento do Lync Server:

    Get-CsSite | Select-Object DisplayName, SiteID

Após criar um pool de aplicativos confiáveis, utilize um comando semelhante para prosseguir com a configuração de um aplicativo Identity e uma porta para o Outlook Web App:

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

No comando anterior, o ApplicationID é simplesmente um identificador amigável usado para distinguir aplicativos confiáveis. O ApplicationID pode ser qualquer cadeia de caracteres de texto que não inclua espaços em branco ou outros caracteres proibidos. (Para garantir que você criará um identificador válido, é recomendado que apenas letras e números sejam utilizados ao especificar um ApplicationId.) O valor atribuído ao parâmetro Porta também é deixado ao critério do administrador: ela pode ser qualquer porta de rede disponível.

Depois de criar o aplicativo confiável, você deve executar o seguinte comando para habilitar as alterações na sua topologia do Lync Server:

    Enable-CsTopology

Observe que você também deve adicionar seu servidor de caixa de correio e acesso de cliente do Exchange a todos os planos de discagem de URI de SIP. Em seguida, isso irá configurar os servidores como Peers SIP confiáveis com a topologia ExUmRouting para o Lync Server.

**Para habilitar envio de mensagens instantâneas no Outlook Web App**

Com o Lync Server corretamente configurado, você pode começar a configurar o Outlook Web App. A primeira etapa nesse processo é habilitar o sistema de mensagens instantâneas em todos os seus diretórios virtuais do Outlook Web App em seus servidores front-ends. (Não é necessário habilitar o sistema de mensagens instantâneas para os diretórios virtuais em seus servidores back-end. Na verdade, é recomendável que você não habilite o sistema de mensagens instantâneas em seus servidores back-end. O recurso de mensagens instantâneas pode ser habilitado nos servidores de acesso para cliente executando o seguinte comando no Shell de gerenciamento do Exchange:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> Por padrão, o envio de mensagens instantâneas é habilitado quando você instala o Outlook Web App; ou seja, a propriedade InstantMessagingEnabled é definida como True. Porém, você ainda precisa executar o comando anterior para definir o tipo de envio de mensagens instantâneas como OCS. Como padrão, InstantMessagingType é definido com o valor Nenhum.



</div>

Em seguida, você deve adicionar as duas linhas a seguir ao arquivo Web. config do Outlook Web App (esse arquivo geralmente está localizado na\\pasta C\\:\\arquivos de\\programas\\Microsoft\\Exchange Server v15 ClientAccess OWA). Essas duas linhas devem ser adicionadas no \<\> nó appSettings no arquivo Web. config, e esse procedimento deve ser executado somente nos servidores back-end nos quais o Outlook Web App tenha sido instalado:

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

No exemplo anterior, o valor de IMCertificateThumbprint deve ser a impressão digital do certificado do Exchange 2013 que está instalado em seus servidores back-end. Você pode recuperar essas informações executando o seguinte comando no Shell de gerenciamento do Exchange:

    Get-ExchangeCertificate

Observe também que o valor atribuído a imservername é o nome de domínio totalmente qualificado do pool do servidor do Lync em que você criou o pool de aplicativos confiáveis para o Outlook Web App.

O certificado que você usa para o Outlook Web App deve ser um certificado confiável para o Lync Server. Uma maneira de garantir que o certificado será confiado pelo Lync Server e pelo Exchange é usar sua autoridade de certificação interna para criar um certificado no servidor de caixa de correio, certificando-se de que o FQDN do servidor é usado para o nome do requerente e que esse FQDN aparece em t campo nome alternativo do certificado. Após o certificado ter sido criado, ele pode ser importado para os seus servidores de back-end. O resultado líquido é que o mesmo certificado é usado para duas finalidades: 1) comunicação entre a Unificação de mensagens do Exchange e o Lync Server; e 2) a integração entre o Outlook Web App e o Lync Server.

Depois de atualizar o arquivo Web. config, você deve executar o seguinte comando no servidor back-end do Exchange para reciclar o pool do Outlook Web App:

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

Se a operação de reciclagem conseguir, você verá a seguinte mensagem no Shell de gerenciamento do Exchange:

    "MSExchangeOWAAppPool" successfully recycled

**Para configurar as políticas de caixa postal do Outlook Web App**

Nesse ponto, você pode usar o comando a seguir para configurar as mensagens instantâneas na política (ou políticas) de caixa de correio apropriada do seu Outlook Web App. Por exemplo, esse comando executado em um de seus servidores de caixa postal habilita as mensagens instantâneas na política padrão:

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

E esse comando habilita as mensagens instantâneas para todas as suas políticas de caixa de correio do Outlook Web App:

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

Depois que a política de caixa de correio tiver sido habilitada, todos os usuários gerenciados por essa política terão total integração entre o Lync Server e o Outlook Web App, contanto que:

  - O usuário tem uma caixa de correio no Exchange 2013.

  - O usuário foi habilitado para o Lync Server 2013.

  - O usuário possua um endereço de proxy SIP válido.

**Desabilitando o sistema de mensagens instantâneas no Outlook Web App**

Como observado anteriormente, o sistema de mensagens instantâneas é habilitado por padrão no Outlook Web App. Isso significa que, se você não integrar o Outlook Web App ao Lync Server, os usuários verão ícones de presença em branco e uma mensagem de erro toda vez que fizerem logon no Outlook Web App. Para evitar esse problema, use o seguinte comando do Shell de gerenciamento do Exchange para desativar o sistema de mensagens instantâneas no Outlook Web App:

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

**Para verificar a integração com o Outlook Web App**

Para verificar se a presença e o sistema de mensagens instantâneas foram integrados ao Outlook Web App, entre no Outlook Web App 2013. No canto superior direito da tela, você verá o seu nome de exibição do Exchange. Se houver um ícone de presença ao lado do seu nome (por exemplo, um ícone verde indicando que o seu status atual está disponível) indica que você integrou com êxito o Lync Server e o Outlook Web App.

Após a autenticação inicial no Outlook Web App, verifique se um evento com a ID 112 (e a fonte sendo Outlook Web App MSExchange) foi gravado no log de eventos no servidor da caixa postal. Esse evento indica que o gerenciador de ponto de extremidade para mensagens instantâneas foi inicializado com sucesso. Se as mensagens instantâneas não parecerem funcionar, no servidor de caixa de correio, procure arquivos de log na pasta C:\\arquivos\\de programas\\Microsoft Exchange\\Server\\v15\\Logging\\OWA instantmessaging. Se qualquer uma das pastas Logging ou InstantMessaging não existir, isso indica que a integração falhou. Nesse caso, você pode usar o rastreamento SIPStack no Lync Server (todos os níveis e todos os sinalizadores) para experimentar e determinar por que a integração falhou.

</div>

<span> </span>

</div>

</div>

</div>

