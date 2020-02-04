---
title: 'Lync Server 2013: criar ou modificar um intervalo de números não atribuídos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90b6068de77a1a32f45afbc34604dc70a4daf58e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>Criar ou modificar um intervalo de números não atribuídos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Use um dos procedimentos a seguir para configurar intervalos de números não atribuídos para o aplicativo de anúncio.

<div>


> [!IMPORTANT]  
> Antes de configurar a tabela de números não atribuídas, você já deve ter definido um ou mais comunicados ou configurar um atendedor automático de UM (Unificação de mensagens) do Exchange.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>Para usar o painel de controle do Lync Server para configurar números de telefone não atribuídos

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Recursos de Voz** e depois, em **Número Não Atribuído**.

4.  Na página **Números não atribuídos**, siga um destes procedimentos:
    
      - Para criar um novo intervalo de números, clique em **Novo**. Em **Nome**, digite o nome que identifica este intervalo de números.
        
        <div>
        

        > [!NOTE]  
        > Depois de confirmar o novo intervalo de números não atribuídos para o banco de dados, não é possível alterar este nome.

        
        </div>
    
      - Para modificar um intervalo de números existente, digite todo o nome do intervalo de órbita, ou parte dele, no campo de pesquisa. Na lista de resultados de intervalos de número, clique no nome desejado, clique em **Editar** e depois, clique em **Exibir Detalhes**.

5.  No primeiro campo **Intervalo Numérico**, digite o número inicial do intervalo e no segundo campo **Intervalo Numérico** digite o número final do intervalo.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>O número inicial do intervalo deve ser menor ou igual ao número final.</P>
    > <LI>
    > <P>Se o número inicial ou o número final do intervalo incluir um número de ramal, ambos os números devem incluir um ramal, que deve ser o mesmo para ambos.</P>
    > <LI>
    > <P>O número deve corresponder à expressão regular (Tel:)? ( \+)? [1-9] \d{0,17}(; Ext = [1-9] \d{0,9})?. Isso significa que o número pode começar com a cadeia de caracteres tel: (se você não especificar essa cadeia de caracteres, ela será adicionada automaticamente), um sinal de adição (+) e um dígito de 1 a 9. O número de telefone pode ter até 17 dígitos e pode ser seguido de um ramal no formato ;ext= seguido do número do ramal.</P></LI></UL>

    
    </div>

6.  Em **Serviço de Comunicado**, execute um dos seguintes procedimentos:
    
      - Clique em **Comunicado**.
    
      - Clique em **UM do Exchange**.

7.  Se, na etapa anterior, você clicou em **Comunicado**, execute:
    
    1.  Em **FQDN do servidor de destino**, clique em **selecionar**, clique na ID de serviço do serviço de aplicativo que executa o aplicativo de anúncio que manipulará as chamadas de entrada para esse intervalo de números não atribuídos e clique em **OK**.
    
    2.  Em **Comunicado**, clique no comunicado a ser reproduzido para este intervalo de números não atribuídos.

8.  Se, na etapa anterior, você clicou em **UM do Exchange**, sob **Número de telefone do Atendedor Automático**, clique em **Selecionar**, clique no número de telefone a ser usado para este intervalo de números não atribuídos e clique em **OK**.

9.  Clique em **OK**.

10. Na página **Número Não Atribuído**, certifique-se de que os intervalos numéricos não atribuídos estejam organizados da ordem que você deseja. Para alterar a posição do intervalo na tabela, clique em um ou mais nomes consecutivos na lista de intervalos e clique na seta para cima ou para baixo.
    
    <div>
    

    > [!TIP]  
    > O Lync Server procura a tabela número não atribuído da parte superior para a inferior e usa o primeiro intervalo que corresponde ao número não atribuído. Se você tem intervalos sobrepostos e um intervalo que especifica uma última ação de reclassificação, certifique-se de que o intervalo esteja no final da lista.

    
    </div>

11. Quando os intervalos numéricos não atribuídos estiverem na ordem desejada, clique em **Confirmar tudo**.

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>Para usar o Windows PowerShell para configurar números de telefone não atribuídos

1.  Faça logon no computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [permissões de configuração de representante no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Use **New-CsUnassignedNumber** para criar um intervalo de números não atribuídos. Use **Set-CsUnassignedNumber** para modificar um intervalo de números não atribuídos existente.
    
    <div>
    

    > [!TIP]  
    > Se você tiver intervalos sobrepostos e desejar que os intervalos sejam aplicados em uma ordem específica, inclua o parâmetro Prioridade. O intervalo com a maior prioridade será aplicado à chamada.

    
    </div>
    
    No linha de comando, siga um destes procedimentos:
    
      - Para criar um intervalo numérico para um serviço de Comunicado, execute:
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - Ou para criar um intervalo numérico para Atendedor Automático do UM do Exchange, execute:
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    Por exemplo:
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    Ou
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    O exemplo a seguir mostra como modificar os números em um intervalo numérico não atribuído existente.
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluir um intervalo de números não atribuído no Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)  


[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

