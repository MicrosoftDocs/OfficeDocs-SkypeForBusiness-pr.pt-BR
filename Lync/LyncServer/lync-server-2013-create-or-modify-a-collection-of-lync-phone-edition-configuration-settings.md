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
ms.openlocfilehash: 8af910ccffd65f14b7f11919ab66ae95acbf4e09
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Criar ou modificar um conjunto de definições de configuração do Lync Phone Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Ao instalar o Lync Server, você obtém uma coleção global de configurações do Lync Phone Edition. Essas configurações se aplicam a todos os dispositivos que executam o Lync Phone Edition em sua implantação. Você pode alterar essas configurações a qualquer momento. Também é possível configurar um novo conjunto de configurações aplicáveis aos dispositivos em um site específico. As configurações de site têm prioridade sobre as configurações globais.

As configurações consistem de nome do conjunto, escopo (global ou site), configuração de segurança SIP, nível de log, nível de QoS (qualidade de serviço) de voz, configuração de bloqueio de telefone e detalhes de bloqueio de telefone, isto é, a) o tamanho do PIN (número de identificação pessoal) de desbloqueio e b) por quanto tempo o telefone deve ficar ocioso antes de bloquear.

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>Para criar uma coleção de definições de configuração do Lync Phone Edition ou editar configurações de uma coleção existente

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Configuração dos Dispositivos**.

4.  Na página **Configuração dos Dispositivos**, siga um destes procedimentos:
    
      - Para criar um novo conjunto de definições de configuração do Lync Phone Edition, clique em **novo**, selecione um site, clique em **OK**, revise as configurações padrão e, se desejar, faça as alterações.
    
      - Para editar qualquer configuração de um conjunto existente, clique no menu **Editar**, clique em **Mostrar detalhes** e faça as alterações.
        
        <div>
        

        > [!TIP]
        > Para voltar a usar as configurações padrão do conjunto global, clique no conjunto global, clique no menu <STRONG>Editar</STRONG>, clique em <STRONG>Excluir</STRONG> e clique em <STRONG>OK</STRONG>. Essa ação não excluirá o conjunto global, apenas irá restaurar os padrões das configurações.

        
        </div>

5.  Clique em **Confirmar**.

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Criando novas definições de configuração do Lync Phone Edition usando cmdlets do Windows PowerShell

Você pode criar definições de configuração do Lync Phone Edition (somente no escopo do site) usando o Windows PowerShell e o cmdlet **New-CsUCPhoneConfiguration** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>Para criar novas definições de configuração do Lync Phone Edition que usem os valores padrão

  - Este comando cria um novo conjunto de configurações de telefone UC para o site Redmond:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Como nenhum parâmetro (além de Identidade, que é obrigatório) foi especificado no comando anterior, o novo conjunto de configurações usará os valores padrão para todas as suas propriedades.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>Para alterar um valor de propriedade única ao criar novas definições de configuração do Lync Phone Edition

  - Para criar configurações que usam valores de propriedade diferentes, basta incluir o parâmetro e valor de parâmetro adequados. Por exemplo, para criar um conjunto de configurações de telefone UC que, por padrão, exijam bloqueio do telefone, use um comando como este:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>Para alterar vários valores de propriedade ao criar novas definições de configuração do Lync Phone Edition

  - É possível modificar valores de várias propriedades incluindo vários parâmetros. Por exemplo, este comando aplica o bloqueio do telefone a também define um tamanho mínimo de PIN de oito dígitos:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

Para obter detalhes, consulte [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluir um conjunto existente de definições de configuração do Lync Phone Edition no Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Definir configurações de segurança para o Lync Phone Edition no Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Impor bloqueio de telefone no Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

