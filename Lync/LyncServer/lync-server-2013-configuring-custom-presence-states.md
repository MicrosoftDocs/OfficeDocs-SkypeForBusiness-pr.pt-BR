---
title: 'Lync Server 2013: configuração de Estados de presença personalizada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f93229ee06a3d45db2478003a18ac22a2e7cf59
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a>Configurando Estados de presença personalizada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-10_

Para definir Estados de presença personalizados no Lync 2013, crie um arquivo de configuração de presença personalizada XML e, em seguida, especifique seu local usando os cmdlets do Shell de gerenciamento do Lync Server **New-CSClientPolicy** ou **set-CSClientPolicy** com o parâmetro CustomStateURL.

Os arquivos de configuração têm as seguintes propriedades:

  - Estados de presença personalizados podem ser configurados com os indicadores de presença disponível, ocupado e não perturbe.

  - O atributo de disponibilidade determina qual indicador de presença é associado ao texto de status do estado personalizado. No exemplo mais adiante neste tópico, o texto de status trabalhando de casa é exibido à direita do indicador de presença verde (disponível).

  - O tamanho máximo do texto de status é de 64 caracteres.

  - É possível adicionar um máximo de quatro Estados de presença personalizados.

  - O parâmetro CustomStateURL especifica o local do arquivo de configuração. No Lync 2013, o modo de alta segurança SIP é habilitado por padrão, portanto, você precisará armazenar o arquivo de configuração de presença personalizada em um servidor Web que tenha HTTPS habilitado. Caso contrário, os clientes do Lync 2013 não poderão se conectar a ele. Por exemplo, um endereço válido seria `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.

<div>


> [!NOTE]  
> Embora não seja recomendado em um ambiente de produção, você pode testar um arquivo de configuração que está localizado em um compartilhamento de arquivo não HTTPS usando a configuração do registro EnableSIPHighSecurityMode para desabilitar o modo de alta segurança SIP no cliente. Em seguida, você pode usar a configuração do registro CustomStateURL para especificar um local não HTTPS para o arquivo de configuração. Observe que o Lync 2013 honra as configurações do registro do Lync 2010, mas a seção do registro foi atualizada. Você deve criar as configurações do registro da seguinte maneira: 
> <UL>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</P>
> <P>Tipo: DWORD</P>
> <P>Dados do valor: 0</P>
> <LI>
> <P>HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</P>
> <P>Tipo: String (REG_SZ)</P>
> <P>Dados de valor (exemplos):\\file://lspool. Corp. contoso. com\LSFileShare\ClientConfigFolder\Presence.xml ou file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</P></LI></UL>



</div>

Localize o estado de presença personalizada especificando um ou mais esquemas de ID de localidade (LCID) no arquivo de configuração XML. O exemplo mais adiante neste tópico mostra a localização em inglês-Estados Unidos (1033), norueguês-Bokmål (1044), francês-França (1036) e Turco (1055). Para obter uma lista de LCIDs, consulte IDs de localidade atribuídas <https://go.microsoft.com/fwlink/p/?linkid=157331>pela Microsoft em.

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a>Para adicionar Estados de presença personalizados ao Lync 2013

1.  Crie um arquivo de configuração XML que use o formato do seguinte exemplo:
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  Salve o arquivo de configuração XML em um servidor Web com HTTPS habilitado. Neste exemplo, o arquivo é chamado de Presence. xml e salvo no local https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.

3.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

4.  No Shell de gerenciamento do Lync Server, defina o local do arquivo de configuração XML usando um comando semelhante ao seguinte:
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  Use o cmdlet **Grant-CSClientPolicy** para atribuir essa nova política aos usuários.

Para obter detalhes, consulte [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) e [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) na documentação do Shell de gerenciamento do Lync Server.

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Por padrão, o Lync Server&nbsp;2013 atualiza as políticas e configurações de cliente a cada três horas.</P>
> <LI>
> <P>Se você quiser continuar usando as configurações de política de grupo de versões anteriores, como o CustomStateURL, o Lync 2013 reconhecerá as configurações se elas estiverem localizadas na nova seção do registro de política (HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Office\15.0\Lync). No entanto, as políticas de cliente baseadas em servidor têm precedência.</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

