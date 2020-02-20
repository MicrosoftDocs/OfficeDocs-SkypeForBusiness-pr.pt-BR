---
title: Atribuindo um certificado de autenticação de servidor para servidor ao Lync Server 2013
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
ms.openlocfilehash: 2d82974f45ab06024f2834609403ed6604067bb2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assigning-a-server-to-server-authentication-certificate-to-microsoft-lync-server-2013"></a>Atribuindo um certificado de autenticação de servidor para servidor ao Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-24_

Para determinar se um certificado de autenticação de servidor para servidor já foi atribuído ao Microsoft Lync Server 2013, execute o seguinte comando no Shell de gerenciamento do Lync Server 2013:

    Get-CsCertificate -Type OAuthTokenIssuer

Se nenhuma informação de certificado é retornada, você deve atribuir um certificado emissor de token antes de poder usar a autenticação servidor para servidor. Como regra geral, qualquer certificado do Lync Server 2013 pode ser usado como seu certificado OAuthTokenIssuer; por exemplo, seu certificado padrão do Lync Server 2013 também pode ser usado como o certificado OAuthTokenIssuer. (O certificado OAUthTokenIssuer também pode ser qualquer certificado de servidor Web que inclua o nome do seu domínio SIP no campo assunto.) Os dois requisitos principais para o certificado usado para a autenticação de servidor para servidor são: 1) o mesmo certificado deve ser configurado como o certificado OAuthTokenIssuer em todos os seus servidores front-end; e 2) o certificado deve ter pelo menos 2048 bits.

Se você não possui um certificado que pode ser usado para autenticação servidor para servidor, é possível obter um novo certificado, importá-lo e usar para autenticação servidor para servidor. Após ter solicitado e obtido o novo certificado, é possível fazer o login para qualquer um de seus Servidores de Front-End e usar um comando do Windows PowerShell semelhante a este para importar e atribuir este certificado:

    Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"

No comando anterior, o parâmetro Path representa o caminho completo para o arquivo de certificado e o parâmetro Password representa a senha atribuída ao certificado. Este procedimento deve ser executado apenas uma vez: O serviço de replicação do Lync Server irá criar automaticamente um conjunto de tarefas programadas que irão criptografar e implantar o certificado em todos os seus Servidores de Front-End.

Em alternativa, é possível usar um certificado existente como seu certificado de autenticação servidor para servidor. (Conforme observado, o certificado padrão pode ser usado como o certificado de autenticação servidor para servidor.) O seguinte par de comandos do Windows PowerShell recupera o valor da propriedade Thumbprint do certificado padrão, use este valor para tornar o certificado padrão o certificado de autenticação servidor para servidor:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x

No comando anterior, o certificado recuperado é configurado para funcionar como o certificado de autenticação servidor para servidor global; isto significa que o certificado será replicado e usado por todos os seus Servidores de Front-End. Novamente, este comando deve ser executado apenas uma vez e apenas em um de seus Servidores de Front-End. Embora todos os Servidores de Front-End devam usar o mesmo certificado, você não deve configurar o certificado OAuthTokenIssuer em cada Servidor de Front-End. Ao invés disso, configure o certificado uma vez, permita que o servidor de replicação do Lync Server cuide da cópia deste certificado em cada servidor.

O cmdlet Set-CsCertificate leva o certificado em questão e configura imediatamente esse certificado para atuar como o certificado OAuthTokenIssuer atual. (Lync Server 2013 mantém duas cópias de um tipo de certificado: o certificado atual e o certificado anterior.) Se você precisar que o novo certificado inicie imediatamente o Act como o certificado OAuthTokenIssuer, você deve usar o cmdlet Set-CsCertificate.

Também é possível usar o cmdlet Set-CsCertificate para "criar" um novo certificado. "Criar" um certificado simplesmente significa que você configura um novo certificado para se tornar o certificado OAuthTokenIssuer atual em um determinado ponto no tempo. Por exemplo, este comando recupera o certificado padrão e configura este certificado para assumir como o certificado OAuthTokenIssuer atual a partir de 1° de julho de 2012:

    $x = (Get-CsCertificate -Type Default).Thumbprint
    Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2012" -Roll

Em 1° de julho de 2012, o novo certificado será configurado como o certificado OAuthTokenIssuer atual e o certificado OAuthTokenIssuer "antigo" será configurado como o certificado anterior.

Se você não deseja usar o Windows PowerShell, é possível também usar o console MMC de Certificados para exportar um certificado de um Servidor de Front-End e importar este mesmo certificado em todos os seus outros Servidores de Front-End. Se você fizer isso, certifique-se de exportar a chave privada junto com o próprio certificado.

<div>


> [!WARNING]
> Neste caso, o procedimento deve ser realizado em cada Servidor de Front-End. Ao exportar e importar certificados dessa maneira, o Lync Server 2013 não replicará esse certificado para cada servidor de front-end.



</div>

Depois que o certificado for importado para todos os seus servidores front-end, esse certificado poderá ser atribuído usando o assistente de implantação do Lync Server em vez do Windows PowerShell. Para atribuir um certificado usando o Assistente de Implantação, conclua as seguintes etapas em um computador onde o Assistente de Implantação foi instalado:

1.  Clique em Iniciar, em todos os programas, em **Microsoft Lync Server 2013**e em **Assistente de implantação do Lync Server**.

2.  No Assistente de Implantação, clique em **Instalar ou Atualizar o Sistema do Lync Server**.

3.  Na página Microsoft Lync Server 2013, clique no botão **executar** no título **etapa 3: solicitar, instalar ou atribuir certificados**. (Observação: Se você já instalou certificados neste computador, o botão **Executar** será chamado **Executar novamente**.)

4.  No Assistente de Certificado, selecione o certificado **OAuthTokenIssuer** e clique em **Atribuir**.

5.  No assistente de Atribuição de Certificado, na página **Atribuição de certificado**, clique em **Avançar**.

6.  Na página **Repositório de Certificado**, selecione o certificado a ser usado para autenticação servidor para servidor e clique em **Avançar**.

7.  Na página Resumo da Atribuição de Certificado, clique em **Avançar**.

8.  Na página Executando Comandos, clique em **Concluir**.

9.  Feche o Assistente de Certificado e Assistente de Implantação.

</div>

<span> </span>

</div>

</div>

</div>

