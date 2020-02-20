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
ms.openlocfilehash: 2d8ee7858e339029fa29c803400ac836871515b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Habilitando ou desabilitando a limpeza de dados arquivados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

No painel de controle do Lync Server 2013, você usa configurações de arquivamento para habilitar e desabilitar a limpeza e configurar como a limpeza é implementada. Isso inclui as seguintes configurações de Arquivamento:

  - Uma configuração global criada por padrão ao implantar o Lync Server 2013.

  - Configurações opcionais de nível do site e pool que você pode criar e usar para especificar como o arquivamento é implementado para sites específicos ou pools.

Inicialmente, as configurações de Arquivamento são definidas ao implantar o Arquivamento, mas você pode alterar, adicionar e excluir configurações depois da implantação. Para obter detalhes sobre como as configurações de arquivamento são implementadas, incluindo quais opções você pode especificar e a hierarquia das configurações de arquivamento, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.

<div>


> [!NOTE]  
> Para usar o arquivamento para usuários hospedados no Lync Server 2013, você deve configurar as políticas de arquivamento para especificar se deseja habilitar o arquivamento para comunicações internas, para comunicações externas ou para ambos. Por padrão, o arquivamento não é habilitado para comunicações internas ou externas. Antes de habilitar o Arquivamento em qualquer política, você deve especificar as configurações apropriadas de Arquivamento para sua Implantação e, opcionalmente, para sites e pools específicos, conforme descrito nesta seção. Para obter detalhes sobre como habilitar o arquivamento, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Configurando e atribuindo políticas de arquivamento no Lync Server 2013</A> na documentação de implantação.<BR>Se você decidir depois de implantar o arquivamento que deseja usar a integração do Microsoft Exchange para armazenar arquivos e dados de arquivamento nos servidores do Exchange 2013 e todos os usuários estão hospedados em seus servidores do Exchange 2013, você deve remover a configuração de banco de dados do SQL Server da sua topologia. Você deve usar o construtor de topologias para fazer isso. Para obter detalhes, consulte <A href="lync-server-2013-changing-archiving-database-options.md">mudança de opções de banco de dados de arquivamento no Lync Server 2013</A> na documentação operações.



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>Para habilitar ou desabilitar a limpeza do arquivamento

1.  A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Configuração do Arquivamento**.

4.  Clique no nome da configuração global, local ou do pool adequado na lista de configurações de arquivamento, clique em **Editar**, em **Exibir detalhes** e faça o seguinte:
    
      - Para habilitar a limpeza, marque a caixa de seleção **Habilitar limpeza de dados de arquivamento** e execute uma das seguintes ações:
        
          - Para limpar todos os registros, clique em **Limpar dados de arquivamento exportados e armazenados após um período máximo de (dias)** e especifique o número de dias.
        
          - Para limpar somente os dados exportados, clique em **Limpar somente dados de arquivamento exportados**.
    
      - Para desabilitar a limpeza, desmarque a caixa de seleção **Habilitar limpeza de dados de arquivamento**.

5.  Clique em **Confirmar**.

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar a limpeza de dados de arquivamento usando cmdlets do Windows PowerShell

Habilitar e desabilitar a limpeza automatizada de dados de arquivamento pode ser gerenciada usando o Windows PowerShell e o cmdlet **set-CsArchivingConfiguration** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>Para habilitar a limpeza de todos os dados de arquivamento

  - Para habilitar a exclusão de todos os dados de arquivamento, defina a propriedade **EnablePurging** para verdadeiro ($True). Por exemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    Depois que esse comando for executado, todos os dias que o Lync Server excluirá todos os registros de arquivamento mais antigos do que o valor especificado para a propriedade **KeepArchivingDataForDays** .

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>Para habilitar a limpeza apenas de dados de arquivamento exportados

  - Para limitar a limpeza aos registros de arquivamento que foram exportados para um arquivo de dados (usando o cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), você também deve definir a propriedade PurgeExportedArchivesOnly como True ($true). Por exemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    Após este comando ser executado, o Lync Server excluirá apenas os registros de arquivamento que atendem a dois critérios: 1) eles são mais antigos do que o valor especificado para a propriedade **KeepArchivingDataForDays** ; e 2) eles foram exportados usando o cmdlet **Export-CsArchivingData** .

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>Para desabilitar a limpeza de todos os dados de arquivamento

  - Para desabilitar a exclusão automática dos registros de arquivamento, defina a propriedade **EnablePurging** para False ($False). Por exemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

Para obter mais informações, incluindo opções adicionais para a limpeza de dados de arquivamento, consulte o tópico de ajuda referente ao cmdlet [set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Configurando e atribuindo políticas de arquivamento no Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

