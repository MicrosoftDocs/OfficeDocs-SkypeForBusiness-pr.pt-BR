---
title: 'Lync Server 2013: impor bloqueio de telefone'
description: 'Lync Server 2013: impor bloqueio de telefone.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5afae4fa27edf9378bacc39a29697c9607b25c07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575597"
---
# <a name="enforce-phone-locking-in-lync-server-2013"></a>Impor bloqueio de telefone no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Os dispositivos do Lync Phone Edition podem ser bloqueados por motivos de segurança. Se você aplicar o bloqueio de telefone, o dispositivo que executa o Lync Phone Edition é bloqueado após um período de tempo que você configura. Quando um telefone é bloqueado, um usuário pode fazer chamadas, mas não pode acessar informações de contato, caixa postal ou logs de chamadas ou usar a pesquisa. Para desbloquear o telefone, o usuário insere um PIN.

Para impor o bloqueio de telefone, habilite e configure-o usando o painel de controle do Lync Server ou cmdlets do Lync Server PowerShell. Você pode impor o bloqueio de telefone globalmente ou apenas dentro do site para o qual ele está configurado.

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>Para configurar e impor o bloqueio de telefone

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Clique**Clientes** e em **Configuração do Dispositivo**.

4.  Na guia **Configuração do Dispositivo**, na lista de configurações do dispositivo, clique duas vezes na configuração de bloqueio do telefone que deseja alterar.

5.  Na caixa de diálogo **Editar Configuração do Dispositivo** verifique se a caixa de seleção **Impor bloqueio do dispositivo** está selecionado.

6.  Em **tamanho mínimo do PIN**, aceite o valor padrão para o número mínimo de dígitos que o PIN de desbloqueio deve conter ou especifique um novo valor. O intervalo para o comprimento do PIN é de quatro a 15 dígitos e o padrão é seis.

7.  Em **tempo limite de bloqueio de telefone**, aceite o valor padrão para o período de tempo mínimo antes que o telefone seja bloqueado ou especifique um novo valor. O intervalo para o tempo limite é de 0 a 60 minutos, e o padrão é 10. Insira o valor no formato HH:MM:SS.

8.  Clique em **Confirmar**.

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Impondo o bloqueio de telefone usando cmdlets do Windows PowerShell

O bloqueio de telefone pode ser imposto usando o cmdlet Set-CsUCPhoneConfiguration. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-phone-locking"></a>Para habilitar o bloqueio de telefone

  - O seguinte comando habilita o bloqueio de telefone para o site Redmond. Para desativar o bloqueio de telefone, defina a propriedade EnforcePhoneLock para Falso ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>Para habilitar o bloqueio de telefone e modificar o tempo limite de bloqueio do telefone

  - Este comando habilita o bloqueio de telefone e também define o tempo limite do bloqueio de telefone para 30 minutos.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>Para habilitar o bloqueio de telefone em toda a organização

  - Neste exemplo, o bloqueio de telefone está habilitado em todas as definições de configuração UC em uso na organização.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciando a autenticação do Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Gerenciando dispositivos, telefones e aplicativos cliente no Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

