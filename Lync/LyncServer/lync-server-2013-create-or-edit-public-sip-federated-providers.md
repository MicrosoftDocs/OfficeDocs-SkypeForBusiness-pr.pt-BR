---
title: 'Lync Server 2013: criar ou editar provedores federados de SIP públicos'
description: 'Lync Server 2013: crie ou edite provedores federados SIP públicos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0ef5850b5e8016e0bd90512db45c2917c16a104
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553857"
---
# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>Criar ou editar provedores federados SIP públicos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

A conectividade de mensagens instantâneas (IM) pública permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores de serviço de IM públicos, incluindo o Windows Live Messenger, o Yahoo \! e o AOL.

Lync Server 2013 tem configurações de provedor público para America Online, Windows Live e Yahoo\! mensagens instantâneas. Cada provedor público é configurado com o nome de domínio totalmente qualificado do servidor de borda do provedor e o nível de verificação padrão **permite que os usuários se comuniquem somente com pessoas em suas listas de contatos que usam esse provedor**.

Como configuração padrão, nenhum dos provedores públicos está habilitado. Você deve concluir o contrato de licença e o provisionamento de trabalho antes de habilitar os provedores públicos. Você pode habilitar o provedor antes de concluir o trabalho de licenciamento e provisionamento. Os usuários não conseguirão se comunicar com os contatos desses provedores até que o trabalho de pré-requisito seja concluído. Para obter detalhes sobre licenciamento e provisionamento de provedores públicos, consulte [Configure Policies to Control Public User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md).

Use o procedimento a seguir para criar ou editar provedores públicos:

<div>

## <a name="to-create-or-edit-public-providers"></a>Para criar ou editar provedores públicos

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Federação e Acesso Externo** e em **Provedores Federados SIP**.

4.  Se você precisar criar um novo provedor público, clique em **novo** e em **provedor público**.

5.  Se for necessário editar uma entrada da lista de provedores públicos, selecione um provedor público, clique em **Editar**e em **Mostrar detalhes**.

6.  Na página **Editar Provedor Federado SIP**, você pode digitar ou editar as seguintes configurações:
    
      - **Habilitar comunicações com este provedor**     A seleção dessa configuração permite mensagens instantâneas com os usuários desse provedor.
    
      - **Nome do provedor:**     Uma propriedade Required, digite o nome do provedor conforme ele será refletido na lista de provedores federados SIP.
    
      - **Serviço de borda de acesso (FQDN):**     Uma propriedade obrigatória, digite o nome de domínio totalmente qualificado do serviço de borda de acesso do provedor que você está configurando. Essas informações são fornecidas como um item padrão e só devem ser alteradas se o provedor público fizer uma alteração no FQDN do serviço de borda de acesso no provedor público.
    
      - **Nível de verificação padrão:**     A configuração padrão, **permitir que os usuários se comuniquem com pessoas em suas listas de contatos, que usam esse provedor** , limitarão a comunicação aos contatos que você aceitou e estão em sua lista de contatos.
        
        Selecionar **Permitir que os usuários se comuniquem com todos que usam este provedor** remove a restrição de que você deve ter recebido e aceitado o convite de um contato. Essa configuração não limita quem pode contatá-lo da rede do provedor público.

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

