---
title: 'Lync Server 2013: Configurando opções de arquivamento para um site'
description: 'Lync Server 2013: Configurando opções de arquivamento para um site.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2db164d7c4c1cdda158387be62c0eb535fac662f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562557"
---
# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a>Configurando opções de arquivamento para um site no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-09_

Você pode especificar opções de arquivamento para serem aplicadas a sites específicos criando e definindo opções em uma configuração de arquivamento para cada um desses sites. Uma configuração de site substitui a configuração global, mas só se aplica ao site específico definido na configuração de site. As configurações de pool substituem as configurações de site

Para obter detalhes sobre como as configurações de arquivamento funcionam, incluindo a hierarquia de configurações globais, de site e de pool, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.

<div>


> [!NOTE]  
> Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento.



</div>

<div>


> [!IMPORTANT]  
> Para habilitar o arquivamento, você deve especificar políticas de arquivamento para controlar o arquivamento de comunicações internas e externas no nível global e, se apropriado, nos níveis de site e de usuário. Se você configurar políticas de nível de usuário, você também deve atribuir as políticas de usuário para usuários específicos. Para obter detalhes sobre como criar e configurar políticas de arquivamento, consulte <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of Internal and external Communications in Lync Server 2013</A> na documentação operações.



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a>Para configurar as opções de arquivamento no nível do site

1.  A partir de uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Lync Server 2013. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.

4.  Na página **Configuração do Arquivamento**, clique em **Novo** e depois em **Configuração do site**.

5.  Em **Selecionar um Site**, selecione o site a ser configurado para arquivamento.

6.  Em **Nova Configuração de Arquivamento**, na caixa da lista suspensa **Configuração do Arquivamento**, execute um dos seguintes procedimentos:
    
      - Para habilitar o arquivamento apenas para sessões de mensagens instantâneas (IM), clique em **Arquivar sessões de IM**.
    
      - Para habilitar o arquivamento para as sessões de IM e conferências, clique em **Arquivar sessões de IM e webconferências**.
    
      - Para desabilitar o arquivamento para a política, clique em **Desabilitar arquivamento**.

7.  Também em **Nova configuração de arquivamento**, faça o seguinte:
    
      - Para bloquear a atividade quando o arquivamento não estiver disponível, marque a caixa de seleção **Bloquear sessões de mensagem instantânea ou conferência da Web se o arquivamento falhar**.
    
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

