---
title: Configurando aplicativos de parceiros no Lync Server 2013 e no Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c60e018a86ec0838791d5fc46845460b5f039f23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Configurando aplicativos de parceiros no Microsoft Lync Server 2013 e no Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-12_

A autenticação de servidor para servidor geralmente envolve três entidades: os dois servidores que precisam se comunicar uns com os outros e um servidor de token de segurança de terceiros. Se dois servidores (por exemplo, servidor A e servidor B) precisarem se comunicar, então ambos os servidores geralmente começam por entrar em contato com um servidor de token e obter um token de segurança mutuamente confiável. Em seguida, o servidor A apresenta esse token de segurança para o servidor B (e vice-versa) como uma maneira de garantir sua autenticidade e seu grau de confiança.

No entanto, esta é uma regra geral. O Lync Server 2013, o Microsoft Exchange Server 2013 e o Microsoft SharePoint Server 2013 não precisam usar um servidor de token de terceiros quando se comunicam uns com os outros; Isso porque esses produtos de servidor podem criar tokens de segurança que podem ser aceitos por um do outro, sem a necessidade de um servidor token separado. (Essa funcionalidade só está disponível no Lync Server 2013, no Exchange 2013 e no SharePoint Server 2013. Se você precisar configurar uma autenticação entre servidores com outros servidores, incluindo outros produtos de servidor da Microsoft, então terá que fazer isso usando um terceiro servidor de token.)

Para configurar a autenticação de servidor para servidor entre o Lync Server e o Exchange, você deve fazer duas coisas: 1) você deve atribuir os certificados apropriados a cada servidor; e 2) você deve configurar cada servidor para ser uma aplicação de parceiro do outro servidor: isso significa que você deve configurar o Lync Server 2013 para ser um aplicativo de parceiro do Exchange 2013 e deve configurar o Exchange 2013 para ser um aplicativo parceiro para o Lync Server 2013.

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Configurando o Lync Server 2013 para ser um aplicativo parceiro do Exchange 2013

A maneira mais fácil de configurar o Lync Server 2013 para ser um aplicativo parceiro com o Exchange 2013 é executar o script Configure-EnterprisePartnerApplication. ps1, um script do Windows PowerShell fornecido com o Exchange 2013. Para executar esse script, você deve fornecer a URL para o documento de metadados de autenticação do Lync Server; Isso normalmente será o nome de domínio totalmente qualificado do pool do Lync Server 2013 seguido do sufixo/Metadata/JSON/1. Por exemplo:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Para configurar o Lync Server como um aplicativo de parceiro, abra o Shell de gerenciamento do Exchange e execute um comando semelhante a este (pressupondo que o Exchange tenha sido instalado na unidade C: e que ele use o caminho de pasta padrão):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

Depois de configurar o aplicativo de parceiro, é recomendável parar e reiniciar os serviços de informações da Internet (IIS) em sua caixa de correio do Exchange e servidores de acesso para cliente. Você pode reiniciar o IIS usando um comando similar a esse, que reinicia o serviço no atl-exchange-001 do computador:

    iisreset atl-exchange-001

Esse comando pode ser executado no Shell de gerenciamento do Exchange ou em qualquer outra janela de comando executada em privilégios de administrador.

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Configurando o Exchange 2013 para ser um aplicativo parceiro do Lync Server 2013

Depois de configurar o Lync Server 2013 para ser um aplicativo parceiro do Exchange 2013, você deve configurar o Exchange para ser um aplicativo parceiro do Lync Server. Isso pode ser feito usando o Shell de gerenciamento do Lync Server e especificando o documento de metadados de autenticação para o Exchange; Isso normalmente será o URI do serviço de descoberta automática do Exchange seguido pelo sufixo/Metadata/JSON/1. Por exemplo:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

No Lync Server, os aplicativos parceiros são configurados usando o cmdlet [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) . Além de especificar o URI dos metadados, você também deve definir o nível de confiança do aplicativo como Full; Isso permitirá que o Exchange represente tanto e qualquer usuário autorizado no território. Por exemplo:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

Você também pode criar um aplicativo de parceiro copiando e modificando o código de script encontrado na documentação de autenticação do servidor para servidor do Lync Server 2013. Confira o artigo [Gerenciamento de autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) para obter mais informações.

Se você configurou com êxito aplicativos de parceiros para o Lync Server e o Exchange, isso significa que você também configurou com êxito a autenticação de servidor para servidor entre os dois produtos. O Lync Server 2013 inclui um cmdlet do Windows PowerShell, [Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), que permite que você verifique se a autenticação do servidor para o servidor foi configurada corretamente e se o serviço de armazenamento do Lync Server pode se conectar ao Exchange 2013. O cmdlet faz isso conectando-se à caixa de correio de um usuário do Exchange 2013, escrevendo um item na pasta de histórico de conversas desse usuário e, opcionalmente, excluindo esse item.

Para testar a integração do Lync Server 2013 e do Exchange 2013, execute um comando semelhante a isso dentro do Shell de gerenciamento do Lync Server:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

No comando anterior, o SipUri representa o endereço SIP de um usuário com uma conta no Exchange 2013; seu comando falhará em uma conta de usuário válida.

Se o teste for bem sucedido e a conectividade for estabelecida, você poderá então prosseguir para configurar recursos opcionais, como integração de arquivamento e repositório de contato unificado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

