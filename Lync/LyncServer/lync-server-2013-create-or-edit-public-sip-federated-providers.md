---
title: 'Lync Server 2013: Criar ou editar fornecedores SIP públicos federados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 876a79e840990afb0c9cf0bae4fc819ec10db5d8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Criar ou editar fornecedores SIP públicos federados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

A conectividade de mensagens instantâneas públicas permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com os usuários de serviços de mensagens instantâneas fornecidos por provedores de serviço de\!mensagens instantâneas públicos, incluindo Windows Live Messenger, Yahoo e AOL.

O Lync Server 2013 tem configurações de provedor público para o America Online, o Windows Live e o Yahoo\! mensagens instantâneas. Cada provedor público é configurado com o nome de domínio totalmente qualificado do servidor de borda do provedor, e o nível de verificação padrão **permite que os usuários se comuniquem somente com as pessoas da lista de contatos que usam esse provedor**.

Como uma configuração padrão, nenhum dos provedores públicos está habilitado. Você deve concluir o contrato de licença e o provisionamento do trabalho antes de habilitar os provedores públicos. Você pode habilitar o provedor antes de concluir o trabalho de licenciamento e provisionamento. Os usuários não poderão se comunicar com os contatos desses provedores até que o trabalho pré-requisito seja concluído. Para obter detalhes sobre licenciamento e provisionamento de provedores públicos, consulte [Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).

Use o procedimento a seguir para criar ou editar provedores públicos:

<div>

## <a name="to-create-or-edit-public-providers"></a>Para criar ou editar provedores públicos

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Federação e acesso externo**e, em seguida, clique em **provedores federados SIP**.

4.  Se você precisar criar um novo provedor público, clique em **novo** e, em seguida, clique em **provedor público**.

5.  Se precisar editar uma entrada da lista de provedores públicos, selecione um provedor público, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

6.  Na página **Editar Provedor federado SIP** , você pode digitar ou editar as seguintes configurações:
    
      - **Habilitar comunicações com este provedor**   selecionar essa configuração habilita mensagens instantâneas com os usuários do provedor.
    
      - **Nome do provedor:**   uma propriedade necessária, digite o nome do provedor como ele será refletido na listagem de provedores federados SIP.
    
      - **Serviço de borda de acesso (FQDN):**   uma propriedade necessária, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor que você está configurando. Essas informações são fornecidas como um item padrão e só devem ser alteradas se o provedor público fizer uma alteração no FQDN do serviço de borda de acesso no provedor público.
    
      - **Nível de verificação padrão:**   a configuração padrão, **permitir que os usuários se comuniquem com as pessoas da lista de contatos que usam esse provedor** limitarão a comunicação com os contatos que você aceitou e estão na sua lista de contatos.
        
        Selecionar **permitir que os usuários se comuniquem com todos que usam esse provedor** remove a restrição que você deve ter recebido e aceito um convite de contato. Esta configuração não limita quem pode contatá-lo na rede do provedor público.

7.  Quando terminar de definir as configurações, clique em **confirmar** para salvar ou clique em **Cancelar** para descartar as alterações.

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurar políticas para controlar o acesso de usuário público no Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

