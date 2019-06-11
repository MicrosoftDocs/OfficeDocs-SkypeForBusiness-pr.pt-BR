---
title: Implantar um Servidor de Borda piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd8fddd611422562c9384a52748623623d4e6f68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Implantar um Servidor de Borda piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Este tópico destaca as configurações de configuração das quais você deve estar ciente antes de implantar seu servidor de borda do Lync Server 2013. Os processos de implantação e configuração do Lync Server 2013 são muito semelhantes ao Lync Server 2010. Esta seção destaca apenas os pontos-chave que você deve considerar como parte da sua implantação de pool piloto. Para obter etapas detalhadas, consulte Implantando o [acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação, que descreve o processo de implantação e também fornece informações de configuração para o acesso de usuários externos.

Ao navegar pelo assistente **definir novo pool de borda** , examine as configurações de chave de configuração mostradas nas etapas a seguir. Observe que apenas algumas páginas do assistente para **definir novo pool de borda** são mostradas.

**Definir um pool de bordas**

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Navegue até o nó do Lync Server 2013. Clique com o botão direito do mouse em **conjuntos de bordas**e clique em **novo pool de bordas**.
    
    ![Definir a caixa de diálogo novo pool de bordas] (images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definir a caixa de diálogo novo pool de bordas")

3.  Um pool de bordas pode ser um **pool de vários computadores** ou um **único pool de computadores**.
    
    ![Definir a caixa de diálogo FQDN do pool de bordas] (images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definir a caixa de diálogo FQDN do pool de bordas")

4.  Na página **selecionar recursos** , não habilite Federação ou Federação do XMPP. A Federação e a Federação do XMPP são roteadas atualmente por meio do servidor de borda do Lync Server 2010 herdado. Esses recursos serão configurados em uma fase posterior da migração.
    
    ![Caixa de diálogo Selecionar recursos] (images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Caixa de diálogo Selecionar recursos")

5.  Em seguida, continue a concluir as seguintes páginas do assistente: **FQDNs externos**, **defina o endereço IP interno**e **defina o endereço IP externo**.

6.  Na página **definir o próximo salto** , selecione o diretor do próximo nó do pool de bordas do Lync Server 2010.
    
    ![Definir a caixa de diálogo salto seguinte] (images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Definir a caixa de diálogo salto seguinte")

7.  Na página **associar front-end ou pool** de mediação, não associe um pool a este pool de bordas no momento. No momento, o tráfego de mídia externo é roteado por meio do servidor de borda herdado do Lync Server 2010. Essa configuração será configurada em uma fase posterior da migração.
    
    ![Caixa de diálogo associar grupos de front-end] (images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Caixa de diálogo associar grupos de front-end")

8.  Clique em **concluir** e **publique** a topologia.

9.  Siga as etapas em [instalar servidores de borda para o Lync server 2013](lync-server-2013-install-edge-servers.md) na documentação de implantação para instalar os arquivos no novo servidor de borda, configurar certificados e iniciar os serviços.

É muito importante que você siga as diretrizes nos tópicos implantando o [acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) na documentação de implantação. Esta seção simplesmente forneceu algumas diretrizes sobre as definições de configuração durante a instalação dessas funções de servidor.

Agora você deve ter um servidor de borda herdado do Lync Server 2010 implantado em paralelo com uma implantação do servidor de borda 2013 do Lync Server. Verifique se as duas implantações estão funcionando corretamente, se os serviços foram iniciados e você pode administrar cada implantação antes de passar para a próxima fase.

</div>

<span> </span>

</div>

</div>

</div>

