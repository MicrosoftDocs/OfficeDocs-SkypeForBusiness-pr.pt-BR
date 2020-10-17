---
title: 'Lync Server 2013: criar definições de configuração do registrador'
description: 'Lync Server 2013: criar definições de configuração do registrador.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ada10302b3c2319e0f713ce2d3bea00b6fed126
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548697"
---
# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>Criar definições de configuração do registrador no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-17_

É possível usar o Registrador para configurar métodos de autenticação do servidor proxy. O protocolo de autenticação que você especificar determina que tipo de desafios os servidores no pool vão gerar para os clientes. Os protocolos disponíveis são:

  - **Kerberos**     Este é o esquema de autenticação de senha mais seguro disponível para clientes, mas que normalmente está disponível somente para clientes corporativos, pois exige conexão do cliente com um centro de distribuição de chaves (controlador de domínio Kerberos). Essa configuração é apropriada se o servidor autenticar somente clientes empresariais.

  - **NTLM**     Esta é a autenticação baseada em senha disponível para clientes que usam um esquema de hash de resposta de desafio na senha. Essa é a única forma de autenticação disponível para clientes sem conectividade com um Centro de distribuição de chaves (controlador de domínio Kerberos), como usuários remotos. Se um servidor autenticar somente usuários remotos, escolha NTLM.

  - **Autenticação**     de certificado Este é o novo método de autenticação quando o servidor precisa obter certificados de clientes do Lync Phone Edition, telefones de área comum, Lync 2013 e o aplicativo Lync da Windows Store. Nos clientes do Lync Phone Edition, depois que um usuário entra e é autenticado com êxito, fornecendo um PIN (número de identificação pessoal), o Lync Server 2013 e, em seguida, provisiona o URI do SIP para o telefone e fornece um certificado assinado do Lync Server ou um certificado de usuário que identifica Joe (ex: SN=joe@contoso.com) para o telefone. Esse certificado é usado para autenticação com o Registrador e Serviços Web.

<div>


> [!NOTE]  
> Recomendamos a habilitação do Kerberos e NTLM quando um servidor suporta autenticação para clientes remotos e empresariais. O Servidor de Borda e os servidores internos se comunicam para assegurar que somente a autenticação NTLM seja oferecida aos clientes remotos. Se somente Kerberos for habilitado nesses servidores, não poderão autenticar usuários remotos. Se os usuários empresariais também autenticarem com base no servidor, o Kerberos será usado.<BR>Se você usar os clientes do aplicativo Lync da Windows Store, deverá habilitar a autenticação de certificado.



</div>

Execute estas etapas para criar um novo Registrador.

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>Para criar novas definições de configuração do registrador

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.

4.  Na página **Registrador**, clique em **Novo**

5.  Em **Selecionar um Serviço **, clique no serviço ao qual o Registrador será aplicado e clique em **OK **.

6.  Em **Nova Configuração do Registrador **, selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes e do suporte em seu ambiente:
    
      - **Habilitar autenticação Kerberos** para que os servidores no pool emitam desafios usando a autenticação Kerberos.
    
      - **Habilitar autenticação NTLM** para que os servidores no pool emitam desafios usando NTLM.
    
      - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados aos clientes.

7.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

