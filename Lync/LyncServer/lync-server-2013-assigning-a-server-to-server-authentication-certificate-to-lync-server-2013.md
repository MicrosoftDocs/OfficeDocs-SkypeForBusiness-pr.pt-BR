---
title: Atribuindo um certificado de autenticação de servidor a servidor ao Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013
ms:assetid: c7413954-2504-47f4-a073-44548aff1c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205253(v=OCS.15)
ms:contentKeyID: 48185367
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06372be3808f3855bc0172cc408308a0c9c9cab2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a>Atribuindo um certificado de autenticação de servidor a servidor ao Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-24_

Para determinar se um certificado de autenticação de servidor para servidor já foi atribuído ao Microsoft Lync Server 2013, execute o seguinte comando no Shell de gerenciamento do Lync Server 2013:

    Get-CsCertificate -Type OAuthTokenIssuer

Se nenhuma informação de certificado for retornada, você deverá atribuir um certificado emissor de token antes de poder usar a autenticação servidor- servidor. Como regra geral, qualquer certificado do Lync Server 2013 pode ser usado como seu certificado do OAuthTokenIssuer; por exemplo, seu certificado padrão do Lync Server 2013 também pode ser usado como o certificado OAuthTokenIssuer. (O certificado OAUthTokenIssuer também pode ser qualquer certificado de servidor Web que inclua o nome do seu domínio SIP no campo assunto.) Os dois requisitos principais para o certificado usado para a autenticação de servidor para servidor são estes: 1) o mesmo certificado deve ser configurado como o certificado OAuthTokenIssuer em todos os seus servidores front-end; e 2) o certificado deve ter pelo menos 2048 bits.

Se você não tiverum certificado que possa ser usado para autenticação servidor-servidor, é possível obter um novo certificado, importá-lo e usar para autenticação servidor-servidor. Depois de solicitar e obter o novo certificado, você pode fazer logon em qualquer um dos seus servidores front-end e usar um comando do Windows PowerShell semelhante a este para importar e atribuir esse certificado:

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

No comando anterior, o parâmetro Path representa o caminho completo para o arquivo de certificado e o parâmetro Password representa a senha atribuída ao certificado. Este procedimento deve ser executado apenas uma vez: o serviço de replicação do Lync Server criará automaticamente um conjunto de tarefas agendadas que descriptografarão e implantarão o certificado em todos os seus servidores front-ends.

Como alternativa, é possível usar um certificado existente como seu certificado de autenticação servidor-servidor. (Conforme observado, o certificado padrão pode ser usado como certificado de autenticação de servidor para servidor.) O seguinte par de comandos do Windows PowerShell recupera o valor da propriedade de impressão digital do certificado padrão e, em seguida, usa esse valor para torná-lo o certificado padrão do certificado de autenticação de servidor para servidor:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

No comando anterior, o certificado recuperado é configurado para funcionar como o certificado de autenticação de servidor para servidor global; Isso significa que o certificado será replicado para e usado por todos os seus servidores front-end. Novamente, esse comando só deve ser executado uma vez e somente em um dos seus servidores front-end. Apesar de todos os servidores front-end precisarem usar o mesmo certificado, você não deve configurar o certificado OAuthTokenIssuer em cada servidor front-end. Em vez disso, configure o certificado uma vez, deixe o servidor de replicação do Lync Server cuidar do cópia desse certificado para cada servidor.

O cmdlet Set-CsCertificate leva o certificado em questão e configura imediatamente esse certificado para atuar como o certificado OAuthTokenIssuer atual. (O Lync Server 2013 mantém duas cópias de um tipo de certificado: o certificado atual e o certificado anterior.) Se você precisar que o novo certificado comece imediatamente a atuar como o certificado OAuthTokenIssuer, use o cmdlet Set-CsCertificate.

Também é possível usar o cmdlet Set-CsCertificate para "criar" um novo certificado. "Criar" um certificado simplesmente significa que você configura um novo certificado para se tornar o certificado OAuthTokenIssuer atual em um determinado ponto no tempo. Por exemplo, esse comando recupera o certificado padrão e, em seguida, configura esse certificado para assumir como o certificado atual do OAuthTokenIssuer a partir de 1 ° de julho de 2012:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

Em 1º de julho de 2012, o novo certificado será configurado como o atual certificado de OAuthTokenIssuer e o certificado de OAuthTokenIssuer "antigo" será configurado como o certificado anterior.

Se não quiser usar o Windows PowerShell, você também pode usar o console MMC de certificados para exportar um certificado de um servidor front-end e, em seguida, importar esse mesmo certificado em todos os outros servidores front-end. Se você fizer isso, certifique-se de exportar a chave privada junto com o próprio certificado.

<div>


> [!WARNING]
> Nesse caso, o procedimento deve ser executado em cada servidor front-end. Ao exportar e importar certificados dessa maneira, o Lync Server 2013 não replicará esse certificado para cada servidor front-end.



</div>

Após a importação do certificado para todos os seus servidores front-end, esse certificado pode ser atribuído usando o assistente de implantação do Lync Server em vez do Windows PowerShell. Para atribuir um certificado usando o Assistente de Implantação, conclua as seguintes etapas em um computador no qual o Assistente de Implantação tenha sido instalado:

1.  Clique em Iniciar, em todos os programas, em **Microsoft Lync Server 2013**e, em seguida, clique em **Assistente de implantação do Lync Server**.

2.  No assistente de implantação, clique em **instalar ou atualizar o sistema do Lync Server**.

3.  Na página Microsoft Lync Server 2013, clique no botão **executar** abaixo do título **etapa 3: solicitar, instalar ou atribuir certificados**. (Observação: Se você já tiver instalado certificados neste computador, o botão **Executar** será chamado **Executar novamente**.)

4.  No Assistente de Certificado, selecione o certificado **OAuthTokenIssuer** e clique em **Atribuir**.

5.  No assistente de Atribuição de Certificado, na página **Atribuição de certificado**, clique em **Avançar**.

6.  Na página **Repositório de Certificado**, selecione o certificado a ser usado para autenticação servidor-servidor e clique em **Avançar**.

7.  Na página Resumo da Atribuição de Certificado, clique em **Avançar**.

8.  Na página Executando Comandos, clique em **Concluir**.

9.  Feche o Assistente de Certificado e Assistente de Implantação.

</div>

<span> </span>

</div>

</div>

</div>

