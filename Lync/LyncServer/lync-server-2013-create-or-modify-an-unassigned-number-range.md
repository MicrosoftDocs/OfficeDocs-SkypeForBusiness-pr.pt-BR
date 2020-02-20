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
ms.openlocfilehash: b423ef547b76241d946e8996da0fe82a5dc27a1f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a>Criar ou modificar um intervalo de números não atribuídos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Use um dos procedimentos a seguir para configurar intervalos de números não atribuídos para o aplicativo de comunicado.

<div>


> [!IMPORTANT]  
> Antes de configurar a tabela de números não atribuídos, você já deve ter definido um ou mais comunicados ou configurar um atendedor automático de um (Unificação de mensagens) do Exchange.



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a>Para usar o painel de controle do Lync Server para configurar números de telefone não atribuídos

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **recursos de voz**e em **número não atribuído**.

4.  Na página **número não atribuído** , siga um destes procedimentos:
    
      - Para criar um novo intervalo de números, clique em **novo**. Em **Nome**, digite um nome de identificação para esse intervalo de números.
        
        <div>
        

        > [!NOTE]  
        > Depois de confirmar o novo intervalo de números não atribuídos para o banco de dados, não será possível alterar esse nome.

        
        </div>
    
      - Para modificar um intervalo de números existente, digite todo ou parte do nome do intervalo de números no campo de pesquisa. Na lista de resultados de intervalos de números, clique no nome desejado, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  No primeiro campo **Intervalo de números** digite o número inicial do intervalo, e no segundo campo **Intervalo de números** digite o número final.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>O número inicial do intervalo deve ser menor ou igual ao número final.</P>
    > <LI>
    > <P>Se o número inicial do intervalo ou o número final do intervalo incluir um número de extensão, os números inicial e final do intervalo precisarão incluir uma extensão e o número de extensão deverá ser o mesmo para os números inicial e final.</P>
    > <LI>
    > <P>O número deve corresponder à expressão regular (Tel:)? ( \+)? [1-9] \d{0,17}(; Ext = [1-9] \d{0,9})?. Isso significa que o número pode começar com a cadeia de caracteres Tel: (se você não especificar essa cadeia de caracteres, ela será automaticamente adicionada para você), um sinal de adição (+) e um dígito de 1 a 9. O número de telefone pode ter até 17 dígitos e pode ser seguido de um ramal no formato ;ext=, seguido do número do ramal.</P></LI></UL>

    
    </div>

6.  Em **Serviço de anúncio**, siga um destes procedimentos:
    
      - Clique em **Comunicado**.
    
      - Click **UM do Exchange**.

7.  Se, na etapa prévia, você clicou em **Comunicado**, faça o seguinte
    
    1.  Em **FQDN do servidor de destino**, clique em **Selecionar**, clique no ID de serviço do serviço do Aplicativo que executa o aplicativo de Comunicado que manipulará as chamadas de entrada para esse intervalo de números não atribuídos e clique em **OK**.
    
    2.  **Comunicado**, clique no comunicado que será reproduzido para esse intervalo de números não atribuídos.

8.  Se, na etapa prévia, você clicou em **UM do Exchange**, em **Número de telefone do Atendedor Automático**, clique em **Selecionar**, clique no número de telefone que será usado para esse intervalo de números não atribuídos e clique em **OK**.

9.  Clique em **OK**.

10. Na página **número não atribuído** , verifique se os intervalos de números não atribuídos estão organizados na ordem desejada. Para alterar a posição de um intervalo na tabela, clique em um ou mais nomes consecutivos na lista de intervalos e, em seguida, clique na seta para cima ou para baixo.
    
    <div>
    

    > [!TIP]  
    > O Lync Server pesquisa a tabela de números não atribuídos de cima para baixo e usa o primeiro intervalo que corresponde ao número não atribuído. Se você tiver intervalos sobrepostos e um intervalo especificar uma ação de último recurso, certifique-se de que o intervalo esteja na parte inferior da lista.

    
    </div>

11. Quando você tiver os intervalos de números não atribuídos na ordem desejada, clique em **confirmar tudo**.

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a>Para usar o Windows PowerShell para configurar números de telefone não atribuídos

1.  Faça logon no computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Use **New-CsUnassignedNumber** para criar um novo intervalo de números não atribuídos. Use **set-CsUnassignedNumber** para modificar um intervalo de números não atribuídos existente.
    
    <div>
    

    > [!TIP]  
    > Se você tiver intervalos sobrepostos e quiser que os intervalos sejam aplicados em uma ordem específica, inclua o parâmetro Priority. O intervalo com a prioridade mais alta será aplicado à chamada.

    
    </div>
    
    Na linha de comando, siga um destes procedimentos:
    
      - Para criar um intervalo numérico para um serviço de anúncio, execute:
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - Ou, para criar um intervalo de números para atendedor automático de UM do Exchange, execute:
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    Por exemplo:
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    Ou
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    O exemplo a seguir mostra como modificar os números em um intervalo de números não atribuídos existente:
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a>Confira também


[Excluir um intervalo de números não atribuídos no Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)  


[New-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

