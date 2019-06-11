---
title: 'Lync Server 2013: criar definições de configuração de registradores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Registrar configuration settings
ms:assetid: eddfbdd2-cfd0-4c03-986e-443d6728db7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182601(v=OCS.15)
ms:contentKeyID: 48185758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 624dc1cfcc8ba8de1f749d6a1a50de9989783070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-registrar-configuration-settings-in-lync-server-2013"></a>Criar definições de configuração do registrador no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-17_

É possível usar o Registrador para configurar métodos de autenticação do servidor proxy. O protocolo de autenticação que você especificar determina que tipo de desafios os servidores no pool vão gerar para os clientes. Os protocolos disponíveis são:

  - **Kerberos**   é o mais forte esquema de autenticação baseado em senha disponível para clientes, mas ele normalmente está disponível somente para clientes corporativos porque requer conexão do cliente a um centro de distribuição de chaves (controlador de domínio Kerberos). Essa configuração será apropriada se o servidor autenticar somente clientes empresariais.

  - **NTLM**   esta é a autenticação baseada em senha disponível para clientes que usam um esquema de hash de resposta de desafio na senha. Essa é a única forma de autenticação disponível para clientes sem conectividade com um Centro de distribuição de chaves (controlador de domínio Kerberos), como usuários remotos. Se um servidor autenticar somente usuários remotos, escolha NTLM.

  - **Autenticação de certificado**   esse é o novo método de autenticação quando o servidor precisa obter certificados de clientes do Lync Phone Edition, telefones de área comuns, Lync 2013 e o aplicativo Lync da Windows Store. Nos clientes do Lync Phone Edition, após o usuário entrar e ter sido autenticado com êxito fornecendo um PIN (número de identificação pessoal), o Lync Server 2013 provisiona o URI SIP para o telefone e provisiona um certificado assinado do Lync Server ou um certificado de usuário que identifica Joe (ex: SN=joe@contoso.com) para o telefone. This certificate is used for authenticating with the Registrar and Web Services.

<div>


> [!NOTE]  
> Recomendamos a habilitação do Kerberos e NTLM quando um servidor suporta autenticação para clientes remotos e empresariais. O Servidor de Borda e os servidores internos se comunicam para assegurar que somente a autenticação NTLM seja oferecida aos clientes remotos. Se somente Kerberos for habilitado nesses servidores, não poderão autenticar usuários remotos. Se os usuários empresariais também autenticarem com base no servidor, o Kerberos será usado.<BR>Se você usará os clientes do aplicativo Lync da Windows Store, será necessário habilitar a autenticação de certificado.



</div>

Execute estas etapas para criar um novo Registrador.

<div>

## <a name="to-create-new-registrar-configuration-settings"></a>Para criar novas configurações de Registrador

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.

4.  Na página **Registrado**, clique em **Novo**

5.  Em **Selecionar um Serviço**, clique no serviço ao qual o Registrador será aplicado e clique em **OK**.

6.  Em **Nova Configuração do Registrador**, selecione uma ou mais das seguintes opções, dependendo dos recursos dos clientes e do suporte em seu ambiente:
    
      - **Habilitar autenticação Kerberos** para que os servidores no pool emitam desafios usando a autenticação Kerberos.
    
      - **Habilitar autenticação NTLM** para que os servidores no pool emitam desafios usando NTLM.
    
      - **Habilitar autenticação de certificado** para que os servidores no pool emitam certificados para os clientes.

7.  Clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

