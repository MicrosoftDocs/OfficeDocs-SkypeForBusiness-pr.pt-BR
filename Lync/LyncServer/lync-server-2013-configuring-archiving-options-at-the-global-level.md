---
title: 'Lync Server 2013: Configurando opções de arquivamento no nível global'
description: 'Lync Server 2013: Configurando opções de arquivamento no nível global.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options at the global level
ms:assetid: bfe415f7-2abf-41ee-a1cb-cf48b2d59c0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205233(v=OCS.15)
ms:contentKeyID: 48185303
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44b8939ec95d00afa2aa7632f4555bc6fef89834
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571737"
---
# <a name="configuring-archiving-options-at-the-global-level-in-lync-server-2013"></a>Configurando opções de arquivamento no nível global no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-10_

Quando você adiciona arquivamento à sua topologia e publica a topologia, o Lync Server cria uma configuração global para arquivamento. Por padrão, nenhuma opção de Arquivamento está ativada na configuração global. Os controles de configuração global que habilitam configurações para a implantação inteira, a não ser que você defina configurações de site ou pool que substituem a configuração global.

Para obter detalhes sobre como as configurações de arquivamento funcionam, incluindo a hierarquia de configurações globais, de site e de pool, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.

<div>


> [!NOTE]  
> Você deve especificar todas as opções apropriadas nas configurações de Arquivamento antes de habilitá-lo.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-global-level"></a>Configurar opções de arquivamento a nível global

1.  Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Lync Server 2013. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.

4.  Na página **Configuração de arquivamento**, clique em **Global**, **Editar** e **Mostrar detalhes**.

5.  Em **Editar configuração de arquivamento - global**, na lista suspensa **Configuração de arquivamento**, selecione uma das seguintes opções de arquivamento:
    
      - **Desativar arquivamento**
    
      - **Arquivar sessões de IM**
    
      - **Arquivar sessões de IM e conferência da Web**

6.  Na página **Editar configuração de arquivamento – global**, faça o seguinte:
    
      - Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de IM (mensagens instantâneas) ou webconferência se ocorrer falha no arquivamento**.
    
      - Para usar o Microsoft Exchange Server para armazenar dados de arquivamento, clique na caixa de seleção **integração com o Microsoft Exchange** .
    
      - Para habilitar a exclusão de dados, marque a caixa de seleção **Habilitar exclusão dos dados de arquivamento** e faça um dos seguintes:
        
          - Para especificar a exclusão após um número específico de dias, clique em **Excluir dados de arquivamento exportados e dados de arquivamento armazenados após uma duração máxima (dias)** e especifique o número de dias.
        
          - Para limitar a exclusão de dados de arquivamento que foram exportados, clique em **Excluir apenas dados de arquivamento exportados**.

7.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

