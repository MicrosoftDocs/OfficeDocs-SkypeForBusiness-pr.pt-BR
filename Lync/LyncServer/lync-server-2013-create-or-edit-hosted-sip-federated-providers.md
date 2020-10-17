---
title: 'Lync Server 2013: criar ou editar provedores federados SIP hospedados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7704074db1b210ca341b05df9fbd02afabbc70a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507488"
---
# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a>Criar ou editar provedores federados SIP hospedados Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

A conectividade de mensagens instantâneas do provedor hospedado permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores hospedados, incluindo o Microsoft 365 e o Lync Online.

Cada provedor hospedado é configurado com o nome de domínio totalmente qualificado do servidor de Borda do provedor e o nível de verificação padrão **Permitir que os usuários se comuniquem somente com pessoas em suas listas de Contatos que usam este provedor**.

Use o procedimento a seguir para criar ou editar provedores hospedados:

<div>

## <a name="to-create-or-edit-hosted-providers"></a>Para criar ou editar provedores hospedados

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Federação e Acesso Externo** e em **Provedores Federados SIP**.

4.  Se for necessário criar um novo provedor hospedado, clique em **Novo** e em **Provedor hospedado**.

5.  Se for necessário editar uma entrada da lista de provedores hospedados, selecione um provedor hospedado, clique em **Editar** e em **Exibir detalhes**.

6.  Na página **Editar Provedor Federado SIP**, você pode digitar ou editar as seguintes configurações:
    
      - **Habilitar comunicações com este provedor**     A seleção dessa configuração permite a comunicação com os usuários desse provedor.
    
      - **Nome do provedor:**     Uma propriedade Required, digite o nome do provedor conforme ele será refletido na lista de provedores federados SIP.
    
      - **Serviço de borda de acesso (FQDN):**     Uma propriedade Required, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor hospedado que você está configurando. Esta informação deve ser fornecida pelo provedor hospedado, e só deve ser alterada se o provedor fizer uma mudança no FQDN do serviço de Borda de Acesso.
    
      - **Nível de verificação padrão:**     A configuração padrão, **permitir que os usuários se comuniquem com pessoas em suas listas de contatos, que usam esse provedor** , limitarão a comunicação aos contatos que você aceitou e estão em sua lista de contatos.
        
        Selecionar **Permitir que os usuários se comuniquem com todos que usam este provedor** remove a restrição de que você deve ter recebido e aceitado o convite de um contato. Esta configuração não limita quem pode entrar em contato com você a partir da rede do provedor hospedado.

7.  Ao concluir a configuração das definições, clique em **Confirmar** para salvar ou em **Cancelar** para descartar as alterações.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

