---
title: 'Lync Server 2013: configurar telefonia para um usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cac7f13d7ba46b9affee1f4d44dd56b167597b80
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>Configurar telefonia para um usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

As configurações de telefonia são algumas das configurações individuais de uma conta de usuário que podem ser configuradas no painel de controle do Lync Server para o usuário (ou seja, se o usuário individual tiver sido habilitado para o Lync Server 2013 e a organização oferecer suporte à telefonia).

As opções de telefonia do usuário do Lync Server incluem o seguinte:

  - **Áudio/vídeo desabilitado**   o usuário não pode fazer chamadas com áudio e vídeo.

  - **Somente PC-PC**   o usuário pode fazer apenas chamadas de áudio e vídeo de PC para PC.

  - **Enterprise Voice**   o usuário pode usar a infraestrutura do Lync Server 2013 para rotear todas as chamadas de entrada e saída. O usuário também pode fazer chamadas PC-PC.

  - **Controle de chamada remota**   o usuário pode usar o Lync Server 2013 para controlar o telefone de mesa e também pode fazer chamadas PC-PC.

Para obter detalhes sobre como configurar telefonia para uma organização, consulte [Configurar telefonia para um usuário no Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) e [implantando o Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) na documentação de implantação.

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>Para configurar telefonia para uma conta de usuário específica

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários**, digite toda ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta que deseja e clique em **Localizar**.

5.  Na tabela, clique na conta de usuário que deseja modificar.

6.  No menu **Editar**, clique em **Modificar**.

7.  Em **Telefonia**, faça o seguinte:
    
      - Para desabilitar as chamadas de áudio e vídeo do usuário, clique em   **Áudio/vídeo desabilitado**.
    
      - Para habilitar a comunicação de áudio PC-PC do usuário, mas não o controle de chamada remota ou o Enterprise Voice, clique em **Somente PC-PC**. Especifique um valor para **URI da Linha** para o telefone que o usuário usa para comunicações de áudio PC-PC.
    
      - Para encaminhar as chamadas telefônicas do usuário usando a infraestrutura do Lync Server 2010 de acordo com a classe de política de serviço, incluindo a comunicação de áudio de PC para PC, clique em **Enterprise Voice**. Em   **URI da Linha**, especifique o número de telefone para Enterprise Voice. Em **Política de plano de discagem** e **Política de Voz **, especifique as políticas apropriadas para o usuário. Para especificar as regras de normalização para conversão de números de telefone discados pelo usuário no formato E.164, selecione o perfil de local apropriado no em **Política de local**.
    
      - Para habilitar o controle de chamada remota, que permite que os usuários controlem a linha de telefone da área de trabalho do Lync Server 2013 para fazer chamadas PC-PC e chamadas de PC para telefone, clique em **controle de chamada remota**. Em **URI da Linha**, especifique o número de telefone para o controle de chamada remota. O usuário deve ter um telefone de mesa e a conexão PBX (central privada de comutação telefônica) para roteamento de chamada.

</div>

<div>

## <a name="see-also"></a>Confira também


[Modificando Propriedades da conta de usuário no Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

