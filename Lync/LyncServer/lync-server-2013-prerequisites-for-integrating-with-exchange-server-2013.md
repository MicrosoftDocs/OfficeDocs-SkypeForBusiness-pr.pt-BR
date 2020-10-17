---
title: 'Lync Server 2013: pré-requisitos para integração com o Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 372c4724275b18dac8db9c050a2ac03753740976
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506738"
---
# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Pré-requisitos para a integração do Microsoft Lync Server 2013 e do Microsoft Exchange Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-04-22_

Para que você possa integrar o Microsoft Lync Server 2013 e o Microsoft Exchange Server 2013, você deve garantir que todas as etapas de pré-requisito foram concluídas. Como você pode esperar, a integração não pode ocorrer até que o Exchange 2013 e o Lync Server 2013 estejam totalmente instalados e em execução. Para obter detalhes sobre como instalar o Exchange, consulte a documentação de planejamento e implantação do Exchange 2013 em [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539) . Para obter detalhes sobre como instalar o Lync Server 2013, consulte a documentação de planejamento e implantação em [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806) .

Após os servidores serem ativados e em execução, você deve atribuir certificados de autenticação de servidor para servidor ao Lync Server 2013 e ao Exchange 2013; esses certificados permitem que o Lync Server e o Exchange troquem informações e se comuniquem entre si. Quando você instala o Exchange 2013, um certificado autoassinado com o nome certificado de autenticação do Microsoft Exchange Server é criado para você. Esse certificado, que pode ser encontrado no repositório de certificados do computador local, deve ser usado para a autenticação de servidor para servidor no Exchange 2013. Para obter detalhes sobre como atribuir certificados no Exchange 2013, consulte "configurar o fluxo de mensagens e o acesso para cliente" em [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540) .

Para o Lync Server 2013, você pode usar um certificado existente do Lync Server como seu certificado de autenticação de servidor para servidor; por exemplo, seu certificado padrão também pode ser usado como o certificado OAuthTokenIssuer. O Lync Server 2013 permite que você use qualquer certificado de servidor Web como o certificado de autenticação de servidor para servidor fornecido por:

  - O certificado inclua o nome de seu domínio SIP no campo de Entidade.

  - O mesmo certificado esteja configurado como o certificado do OAuthTokenIssuer em todos os seus servidores Front-End.

  - O certificado tenha no mínimo 2048 bits.

Para obter detalhes sobre certificados de autenticação de servidor para servidor para o Microsoft Lync Server 2013, consulte [atribuir um certificado de autenticação de servidor para servidor ao Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).

Depois que os certificados tiverem sido atribuídos, você deve configurar o serviço de descoberta automática no Exchange 2013. No Exchange 2013, o serviço de descoberta automática configura perfis de usuário e fornece acesso aos serviços do Exchange quando os usuários fazem logon no sistema. Os usuários apresentam seus endereços de email e senhas ao serviço de descoberta automática; por sua vez, os serviços fornecem aos usuários informações como:

  - Informações de conexão para conectividade interna e externa para o Exchange 2013.

  - A localização do servidor da Caixa de Correio do usuário.

  - URLs para recursos do Outlook como informações de livre/ocupado, Unificação de Mensagens e o catálogo de endereços offline.

  - Configurações do servidor do Outlook Anywhere.

O serviço de descoberta automática deve ser configurado para que você possa integrar o Lync Server 2013 e o Exchange 2013. Você pode verificar se o serviço de descoberta automática foi ou não configurado executando o seguinte comando no Shell de gerenciamento do Exchange e verificando o valor da propriedade AutoDiscoverServiceInternalUri:

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

Caso o valor esteja em branco, você deve atribuir um URI ao serviço de descoberta automática:

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

Você pode atribuir o URI de descoberta automática executando um comando similar a este:

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

Para obter detalhes sobre o serviço de descoberta automática, consulte "Understanding the autodiscover Service" em [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542) .

Depois que o serviço de descoberta automática tiver sido configurado, você deve modificar as definições de configuração do Lync Server OAuth; Isso garante que o Lync Server saiba onde encontrar o serviço de descoberta automática. Para modificar as definições de configuração do OAuth no Lync Server 2013, execute o seguinte comando no Shell de gerenciamento do Lync Server. Ao executar esse comando, verifique se você especificou o URI para o serviço de descoberta automática em execução no seu servidor do Exchange e se você usa o **autodiscover. svc** para apontar para o local do serviço em vez de **autodiscover.xml** (que aponta para o arquivo XML usado pelo serviço):

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> O parâmetro Identity no comando anterior é opcional; Isso ocorre porque o Lync Server permite que você tenha apenas uma única coleção global de definições de configuração OAuth. Dentre outras coisas, isso significa que você pode configurar a URL de descoberta automática usando este comando um pouco mais simples:<BR>Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl " https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc "<BR>Caso não esteja familiarizado com a tecnologia, o OAuth é um protocolo de autorização padrão usado por vários websites importantes. Com o OAuth, as credenciais de usuário e senhas não são passadas de um computador a outro. Ao invés disso, a autenticação e autorização são baseadas na troca de tokens de segurança; estas tokens concedem acesso a um conjunto específico de recursos por um período determinado de tempo.



</div>

Além de configurar o serviço de descoberta automática, você também deve criar um registro DNS para o serviço que aponta para o seu servidor Exchange. Por exemplo, se o serviço de descoberta automática estiver localizado em autodiscover.litwareinc.com, você precisará criar um registro DNS para autodiscover.litwareinc.com que resolva o nome de domínio totalmente qualificado do seu servidor do Exchange (por exemplo, atl-exchange-001.litwareinc.com).

</div>

<span> </span>

</div>

</div>

</div>

