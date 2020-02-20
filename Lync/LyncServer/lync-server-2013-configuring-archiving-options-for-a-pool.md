---
title: 'Lync Server 2013: Configurando opções de arquivamento para um pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f59ad3c768db0ea133337b747c073ee2e0c56b1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a>Configurando opções de arquivamento para um pool no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-10_

Você deve especificar as opções de Arquivamento que serão aplicadas a pools específicos criando e configurando opções em uma configuração de Arquivamento para cada um desses pools. Uma configuração de pool substitui a configuração global e de site, mas somente para o pool especificado na configuração de pool.

Para obter detalhes sobre como as configurações de arquivamento funcionam, incluindo a hierarquia de configurações globais, de site e de pool, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.

<div>


> [!NOTE]  
> Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento. Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a>Configurar opções de arquivamento no nível do pool

1.  Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Lync Server 2013. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.

4.  Na página **Configuração de arquivamento**, clique em **Nova** e em **Configuração de pool**.

5.  Em **Selecionar um serviço**, selecione o pool que será configurado para arquivamento.

6.  Em **Nova configuração de arquivamento**, na lista suspensa **Configuração de arquivamento**, selecione uma das seguintes opções de arquivamento:
    
      - **Desativar arquivamento**
    
      - **Arquivar sessões de IM**
    
      - **Arquivar sessões de IM e conferência da Web**

7.  Na página **Nova configuração de arquivamento**, faça o seguinte:
    
      - Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de IM (mensagens instantâneas) ou webconferência se ocorrer falha no arquivamento**.
    
      - Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique na caixa de seleção **integração com o Microsoft Exchange** .
    
      - Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:
        
          - Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.
        
          - Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.

8.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

