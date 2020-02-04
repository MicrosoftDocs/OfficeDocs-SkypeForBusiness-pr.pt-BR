---
title: 'Lync Server 2013: habilitando ou desabilitando a limpeza de dados arquivados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b06d21cc0154ea57bc028c87c835e4de9a00f1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Habilitar ou desabilitar a limpeza de dados arquivados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

No painel de controle do Lync Server 2013, você usa configurações de arquivamento para habilitar e desabilitar a limpeza e configurar como a limpeza é implementada. Isso inclui as seguintes configurações de arquivamento:

  - Uma configuração global criada por padrão quando você implanta o Lync Server 2013.

  - Configurações opcionais de nível de site e de pool que você pode criar e usar para especificar como o arquivamento é implementado para sites ou pools específicos.

Inicialmente, você define o arquivamento de configurações ao implantar o arquivamento, mas pode alterar, adicionar e excluir configurações após a implantação. Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia de configurações de arquivamento, consulte [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações.

<div>


> [!NOTE]  
> Para usar o arquivamento para usuários que são hospedados no Lync Server 2013, configure as políticas de arquivamento para especificar se o arquivamento deve ser habilitado para comunicações internas, para comunicações externas ou para ambos. Por padrão, o arquivamento não está habilitado para comunicações internas ou externas. Antes de habilitar o arquivamento em qualquer política, você deve especificar as configurações de arquivamento adequadas para sua implantação e, opcionalmente, para sites e pools específicos, conforme descrito nesta seção. Para obter detalhes sobre como habilitar o arquivamento, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurar e atribuir políticas de arquivamento no Lync Server 2013</A> na documentação de implantação.<BR>Se você decidir após implantar o arquivamento em que deseja usar a integração do Microsoft Exchange para armazenar arquivos de arquivamento e arquivos nos servidores Exchange 2013 e todos os usuários estiverem hospedados em seus servidores Exchange 2013, você deve remover a configuração de banco de dados do SQL Server da sua topologia. Você deve usar o construtor de topologias para fazer isso. Para obter detalhes, consulte <A href="lync-server-2013-changing-archiving-database-options.md">alterando as opções de arquivamento de banco de dados no Lync Server 2013</A> na documentação de operações.



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>Para habilitar ou desabilitar a limpeza para arquivamento

1.  Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Configuração de Arquivamento**.

4.  Clique no nome da configuração apropriada de pool, site ou global na lista de configurações de arquivamento, clique em **Editar**, **Mostrar detalhes** e faça o seguinte:
    
      - Para habilitar a limpeza, marque a caixa de seleção **Habilitar limpeza de dados de arquivamento** e execute uma das seguintes ações:
        
          - Para limpar todos os registros, clique em **Limpar dados de arquivamento exportados e armazenados após um período máximo de (dias)** e especifique o número de dias.
        
          - Para limpar somente os dados exportados, clique em **Limpar somente dados de arquivamento exportados**.
    
      - Para desabilitar a limpeza, desmarque a caixa de seleção **Habilitar limpeza de dados de arquivamento**.

5.  Clique em **Confirmar**.

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar o descarte do arquivamento de dados usando cmdlets do Windows PowerShell

Habilitar e desabilitar a limpeza automática de dados de arquivamento pode ser gerenciado usando o Windows PowerShell e o cmdlet **set-CsArchivingConfiguration** . Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>Para habilitar a remoção de todos os dados de arquivamento

  - Para habilitar a remoção de todos os dados de arquivamento defina a propriedade **EnablePurging** como true ($true). Por exemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    Depois que esse comando for executado, cada dia do Lync Server limpará todos os registros de arquivamento anteriores ao valor especificado para a propriedade **KeepArchivingDataForDays** .

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>Para habilitar a limpeza apenas dos dados de arquivamento exportados

  - Para limitar a limpeza para arquivar registros que foram exportados para um arquivo de dados (usando o cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), você também deve definir a propriedade PurgeExportedArchivesOnly como True ($true). Por exemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    Depois que esse comando for executado, o Lync Server somente limpará o arquivamento de registros que atendam a dois critérios: 1) eles são mais antigos do que o valor especificado para a propriedade **KeepArchivingDataForDays** ; e 2) eles foram exportados usando o cmdlet **Export-CsArchivingData** .

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>Para desativar a remoção de todos os dados de arquivamento

  - Para desabilitar a limpeza automatizada de registros de arquivamento, defina a propriedade **EnablePurging** como False ($false). Por exemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

Para obter mais informações, incluindo opções adicionais para limpar dados de arquivamento, consulte o tópico da ajuda para o cmdlet [set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Configurar e atribuir políticas de arquivamento no Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

