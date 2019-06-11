---
title: 'Lync Server 2013: configurar a telefonia de um usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97f4fc79b871a962fe498d6dbd908b75f6b2fecd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>Configurar a telefonia para um usuário no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

As configurações de telefonia são algumas das configurações individuais de uma conta de usuário que podem ser configuradas no painel de controle do Lync Server para o usuário (ou seja, se o usuário individual tiver sido habilitado para o Lync Server 2013 e a organização oferecer suporte a telefonia).

As opções de telefonia do usuário do Lync Server incluem o seguinte:

  - **Áudio/vídeo desabilitado**   o usuário não pode fazer chamadas com áudio e vídeo.

  - **PC para PC somente**   o usuário pode fazer chamadas de áudio e vídeo de PC para PC.

  - **Enterprise Voice**   o usuário pode usar a infraestrutura do Lync Server 2013 para direcionar todas as chamadas de entrada e saída. O usuário também pode fazer chamadas de PC para PC.

  - **Controle de chamada remota**   o usuário pode usar o Lync Server 2013 para controlar o telefone de mesa e também pode fazer chamadas de PC para PC.

Para obter detalhes sobre como configurar a telefonia de uma organização, consulte [Configurar a telefonia de um usuário no Lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) e [implantação do Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) na documentação de implantação.

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>Para configurar a telefonia para uma conta de usuário específica

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários** , digite toda ou a primeira parte do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja e clique em **Localizar **.

5.  Na tabela, clique na conta de usuário que você deseja modificar.

6.  No menu **Editar** , clique em **Modificar**.

7.  Em **telefonia**, faça o seguinte:
    
      - Para desativar as chamadas de áudio e vídeo para o usuário, clique em **áudio/vídeo desabilitado**.
    
      - Para habilitar as comunicações de áudio PC para PC para o usuário, mas não o controle de chamada remota ou o Enterprise Voice, clique em **PC para PC somente**. Especifique um valor para o **URI da linha** para o telefone que o usuário usa para comunicações de áudio PC para PC.
    
      - Para encaminhar as chamadas telefônicas do usuário usando a infraestrutura do Lync Server 2010 de acordo com a classe de política de serviço, incluindo comunicação de áudio PC para PC, clique em **Enterprise Voice**. Em **URI da linha**, especifique o número de telefone do Enterprise Voice. Em **política de plano** de discagem e **política de voz**, especifique as políticas adequadas para o usuário. Para especificar as regras de normalização para a tradução de números de telefone discados pelo usuário para o formato E. 164, selecione o perfil de localização apropriado na **política de localização**.
    
      - Para habilitar o controle de chamada remota, que permite que os usuários controlem a linha de telefone da área de trabalho do Lync Server 2013 para fazer chamadas de PC para PC e chamadas de PC para telefone, clique em **controle de chamada remota**. Em **URI de linha**, especifique o número de telefone para o controle de chamada remota. O usuário deve ter uma conexão de telefone de mesa e PBX (Private Branch Exchange) para roteamento de chamadas.

</div>

<div>

## <a name="see-also"></a>Confira também


[Modificando Propriedades de conta de usuário no Lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

