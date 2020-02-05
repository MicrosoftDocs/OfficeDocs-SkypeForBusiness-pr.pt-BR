---
title: Criar ou modificar uma coleção de definições de configuração do Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b3eaf347693d079ef713716c5ebd0d8c470feef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Criar ou modificar uma coleção de definições de configuração do Lync Phone Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Ao instalar o Lync Server, você obtém uma coleção global das configurações do Lync Phone Edition. Essas configurações se aplicam a todos os dispositivos que executam o Lync Phone Edition na sua implantação. Você pode alterar essas configurações a qualquer momento. Você também pode configurar um novo conjunto de configurações que se aplicam aos dispositivos em um site específico. As configurações do site têm precedência sobre as configurações globais.

As definições de configuração consistem no nome da coleção, escopo (global ou site), configuração de segurança SIP, nível de log, nível de qualidade do serviço (QoS), configuração de bloqueio de telefone e detalhes do bloqueio por telefone, ou seja, por quanto tempo o número de identificação pessoal do desbloquear ( PIN) deve ser e b) o telefone permanecerá ocioso antes de se bloquear.

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>Para criar um conjunto de definições de configuração do Lync Phone Edition ou editar configurações de uma coleção existente

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração de dispositivo** .

4.  Na página **configuração de dispositivo** , siga um destes procedimentos:
    
      - Para criar uma nova coleção de definições de configuração do Lync Phone Edition, clique em **novo**, selecione um site, clique em **OK**, examine as configurações padrão e, se quiser, faça as alterações.
    
      - Para editar qualquer uma das configurações em uma coleção existente, clique na coleção, clique no menu **Editar** , clique em **Mostrar detalhes**e, em seguida, faça as alterações.
        
        <div>
        

        > [!TIP]
        > Para voltar a usar as configurações padrão para a coleção global, clique na coleção global, clique no menu <STRONG>Editar</STRONG> , clique em <STRONG>excluir</STRONG>e, em seguida, clique em <STRONG>OK</STRONG>. Isso não excluirá a coleção global; Ele simplesmente redefine as configurações para os padrões.

        
        </div>

5.  Clique em **Confirmar**.

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Criando novas configurações do Lync Phone Edition usando cmdlets do Windows PowerShell

Você pode criar as configurações de configuração do Lync Phone Edition (apenas em escopo do site) usando o Windows PowerShell e o cmdlet **New-CsUCPhoneConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>Para criar novas definições de configuração do Lync Phone Edition que usam os valores padrão

  - Esse comando cria um novo conjunto de definições de configuração de telefone UC para o site de Redmond:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Como nenhum parâmetro (além do parâmetro obrigatório Identity) foi especificado no comando anterior, o novo conjunto de definições de configurações usará os valores padrões para todas suas propriedades.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>Para alterar um único valor de propriedade ao criar novas configurações de configuração do Lync Phone Edition

  - Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e valor de parâmetro adequados. Por exemplo, para criar um conjunto de configurações de configuração de telefone UC que, por padrão, exigem o bloqueio por telefone, use um comando como este:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>Para alterar vários valores de propriedade durante a criação de novas configurações do Lync Phone Edition

  - Vários valores de propriedade podem ser modificados incluindo vários parâmetros. Por exemplo, esse comando reforça o bloqueio de telefone e também define o comprimento mínimo do PIN como 8 dígitos:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

Para obter detalhes, consulte [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluir uma coleção existente de definições de configuração do Lync Phone Edition no Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Definir configurações de segurança para o Lync Phone Edition no Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Impor o bloqueio de telefone no Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

