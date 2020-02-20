---
title: Configurando aplicativos parceiros no Lync Server 2013 e no Exchange Server 2013
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
ms.openlocfilehash: fca5fe648ecfb00c7ef7bcb84948a68e4386bbf3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134697"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Configurando aplicativos parceiros no Microsoft Lync Server 2013 e no Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-12_

A autenticação entre servidores geralmente envolve três entidades: os dois servidores que precisam se comunicam entre si e um terceiro servidor de token de segurança. Se dois servidores (por exemplo, Servidor A e Servidor B) precisarem se comunicar, então ambos geralmente iniciam entrando em contato com o servidor de token, obtendo um token de segurança mutuamente confiável. O Servidor A então apresenta esse token de segurança ao Servidor B (e vice-versa), como uma forma de garantir autenticidade e confiabilidade.

No entanto, esta é uma regra geral. O Lync Server 2013, o Microsoft Exchange Server 2013 e o Microsoft SharePoint Server 2013 não precisam usar um servidor de token de terceiros ao se comunicar uns com os outros; Isso ocorre porque esses produtos de servidor podem criar tokens de segurança que podem ser aceitos por um do outro, sem a necessidade de um servidor token separado. (Esse recurso só está disponível no Lync Server 2013, no Exchange 2013 e no SharePoint Server 2013. Se você precisar configurar uma autenticação entre servidores com outros servidores, incluindo outros produtos de servidor da Microsoft, então será necessário fazer isso usando um terceiro servidor de token.

Para configurar a autenticação de servidor para servidor entre o Lync Server e o Exchange, você deve fazer duas coisas: 1) você deve atribuir os certificados apropriados a cada servidor; e 2) você deve configurar cada servidor para ser um aplicativo parceiro do outro servidor: isso significa que você deve configurar o Lync Server 2013 para ser um aplicativo parceiro para o Exchange 2013, e você deve configurar o Exchange 2013 para ser um aplicativo parceiro para o Lync Server 2013.

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Configurando o Lync Server 2013 para ser um aplicativo parceiro para o Exchange 2013

A maneira mais fácil de configurar o Lync Server 2013 para ser um aplicativo parceiro com o Exchange 2013 é executar o script configure-enterprisepartnerapplication. ps1, um script do Windows PowerShell que acompanha o Exchange 2013. Para executar esse script, você deve fornecer a URL para o documento de metadados de autenticação do Lync Server; Normalmente, o nome de domínio totalmente qualificado do pool do Lync Server 2013, seguido do sufixo/Metadata/JSON/1. Por exemplo:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Para configurar o Lync Server como um aplicativo parceiro, abra o Shell de gerenciamento do Exchange e execute um comando semelhante a este (supondo que o Exchange tenha sido instalado na unidade C: e que ele use o caminho de pasta padrão):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

Após configurar o aplicativo parceiro, é recomendável que você pare e reinicie o IIS (serviços de informações da Internet) na caixa de correio do Exchange e nos servidores de acesso para cliente. Você pode reiniciar o IIS usando um comando similar a este, que reinicia o serviço no computador atl-exchange-001:

    iisreset atl-exchange-001

Este comando pode ser executado de dentro do Shell de gerenciamento do Exchange ou de qualquer outra janela de comando executada sob privilégios de administrador.

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Configurando o Exchange 2013 para ser um aplicativo parceiro para o Lync Server 2013

Depois de configurar o Lync Server 2013 para ser um aplicativo parceiro para o Exchange 2013, configure o Exchange para ser um aplicativo parceiro para o Lync Server. Isso pode ser feito usando o Shell de gerenciamento do Lync Server e especificando o documento de metadados de autenticação para o Exchange; Este será tipicamente o URI do serviço de descoberta automática do Exchange seguido pelo sufixo/Metadata/JSON/1. Por exemplo:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

No Lync Server, os aplicativos parceiros são configurados usando o cmdlet [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) . Além de especificar o URI dos metadados, você também deve definir o nível de confiança do aplicativo como completo; Isso permitirá que o Exchange represente tanto e qualquer usuário autorizado no realm. Por exemplo:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

Como alternativa, você pode criar um aplicativo de parceiro copiando e modificando o código de script encontrado na documentação de autenticação de servidor para servidor do Lync Server 2013. Confira o artigo [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) para obter mais informações.

Se você configurou com êxito aplicativos parceiros para o Lync Server e o Exchange, isso significa que você também configurou com êxito a autenticação de servidor para servidor entre os dois produtos. O Lync Server 2013 inclui um cmdlet do Windows PowerShell, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), que permite verificar se a autenticação de servidor para servidor foi configurada corretamente e se o serviço de armazenamento do Lync Server pode se conectar ao Exchange 2013. O cmdlet faz isso conectando-se à caixa de correio de um usuário do Exchange 2013, gravar um item na pasta de histórico de conversa desse usuário e, opcionalmente, excluir esse item.

Para testar a integração do Lync Server 2013 e do Exchange 2013, execute um comando semelhante a este no Shell de gerenciamento do Lync Server:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

No comando anterior, o SipUri representa o endereço SIP de um usuário com uma conta no Exchange 2013; o comando falhará se não for uma conta de usuário válida.

Se o teste for bem sucedido e a conectividade for estabelecida, será possível então prosseguir para configurar recursos opcionais, como integração de arquivamento e o armazenamento de contato unificado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

