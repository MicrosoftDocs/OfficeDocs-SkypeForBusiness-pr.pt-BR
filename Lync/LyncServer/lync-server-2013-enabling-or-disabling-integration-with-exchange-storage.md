---
title: 'Lync Server 2013: habilitando ou desabilitando a integração com o armazenamento do Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d20aa4cfc8ab86dfe12458fbd9ce04e11fc4442e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522388"
---
# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a>Habilitar ou desabilitar a integração do Lync Server 2013 com o armazenamento do Exchange

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-09_

No painel de controle do Lync Server 2013, você usa configurações de arquivamento para habilitar e desabilitar a integração com o armazenamento do Exchange. Isso inclui as seguintes configurações de Arquivamento:

  - Uma configuração global criada por padrão ao implantar o Lync Server 2013.

  - Configurações opcionais de nível do site e pool que você pode criar e usar para especificar como o arquivamento é implementado para sites específicos ou pools.

Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia das configurações de arquivamento, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a>Para habilitar ou desabilitar a integração com o armazenamento do Microsoft Exchange

1.  A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.

4.  Clique no nome da configuração do pool, local ou global adequada na lista de configurações de arquivamento, clique em **Editar**, em **Exibir detalhes** e faça o seguinte:
    
      - Para habilitar a integração com o armazenamento 2013 do Exchange, marque a caixa de seleção integração com o **Microsoft Exchange** .
    
      - Para desabilitar a integração com o armazenamento do Exchange 2013, desmarque a caixa de seleção integração com o **Exchange** .

5.  Clique em **Confirmar**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

