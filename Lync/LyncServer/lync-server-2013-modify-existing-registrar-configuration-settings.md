---
title: 'Lync Server 2013: modificar as definições de configuração de registradores existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify existing Registrar configuration settings
ms:assetid: a8931511-3e66-49ed-a3ec-03bcd61ce1f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182566(v=OCS.15)
ms:contentKeyID: 48185095
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42629c027157c33bc9431d04d493019e4907d87b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-registrar-configuration-settings-in-lync-server-2013"></a>Modificar as definições de configuração do registrador existentes no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Você pode usar o Registrador para configurar protocolos de autenticação de servidor proxy. Para obter informações sobre os protocolos disponíveis, consulte [criar configurações de registrador de configuração no Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).

<div>


> [!NOTE]  
> Recomendamos a habilitação do Kerberos e NTLM quando um servidor suporta autenticação para clientes remotos e empresariais. O Servidor de Borda e os servidores internos se comunicam para assegurar que somente a autenticação NTLM seja oferecida aos clientes remotos. Se somente Kerberos for habilitado nesses servidores, não poderão autenticar usuários remotos. Se os usuários empresariais também autenticarem com base no servidor, o Kerberos será usado.



</div>

Siga estas etapas para modificar um Registrador Avançado existente.

<div>

## <a name="to-modify-existing-registrar-configuration-settings"></a>Para modificar as configurações existentes do Registrador

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.

4.  Na página **Registrador Avançado**, clique em um serviço, em **Editar** e em **Exibir detalhes**.

5.  Em **Editar Configuração do Registrador Avançado**, selecione um ou mais dos itens a seguir, dependendo dos recursos dos clientes e do suporte em seu ambiente:
    
      - **Habilitar autenticação Kerberos** para que os servidores no pool emitam desafios usando a autenticação Kerberos.
    
      - **Habilitar autenticação NTLM** para que os servidores no pool emitam desafios usando NTLM.
    
      - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.

6.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

