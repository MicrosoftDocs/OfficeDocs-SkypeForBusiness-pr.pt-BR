---
title: 'Lync Server 2013: impor o bloqueio de telefone'
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
ms.openlocfilehash: 9c781c09db1834d85a1df4532d1484e43d74ca48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a>Impor o bloqueio de telefone no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Os dispositivos do Lync Phone Edition podem ser bloqueados por motivos de segurança. Se você aplicar o bloqueio de telefone, o dispositivo que executa o Lync Phone Edition será bloqueado após um período de tempo que você configurar. Quando um telefone está bloqueado, um usuário pode fazer chamadas, mas não pode acessar o calendário e informações de contato, caixa postal ou logs de chamadas ou usar a pesquisa. Para desbloquear o telefone, o usuário insere um PIN.

Para impor o bloqueio de telefone, habilite e configure-o usando o painel de controle do Lync Server ou cmdlets do PowerShell do Lync Server. Você pode impor o bloqueio de telefone globalmente ou somente dentro do site para o qual ele está configurado.

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>Para configurar e impor o bloqueio do telefone

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Clique em **clientes**e em **configuração de dispositivo**.

4.  Na guia **configuração de dispositivo** , na lista de configurações de dispositivo, clique duas vezes na configuração para a qual você deseja alterar as configurações de bloqueio de telefone.

5.  Na caixa de diálogo **Editar configuração de dispositivo** , verifique se a caixa de seleção **impor bloqueio de dispositivo** está marcada.

6.  No **comprimento mínimo do PIN**, aceite o valor padrão para o número mínimo de dígitos que o PIN de desbloqueio deve conter ou especifique um novo valor. O intervalo para o comprimento do pino é de quatro a 15 dígitos, e o padrão é seis.

7.  Em **tempo limite de bloqueio de telefone**, aceite o valor padrão pelo período de tempo mínimo antes de o telefone bloquear a si mesmo ou especifique um novo valor. O intervalo para o tempo limite é de 0 a 60 minutos, e o padrão é 10. Insira o valor no formato HH:MM:SS.

8.  Clique em **Confirmar**.

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Impondo o bloqueio de telefone usando cmdlets do Windows PowerShell

O bloqueio de telefone pode ser imposto usando o cmdlet Set-CsUCPhoneConfiguration. Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-enable-phone-locking"></a>Para ativar o bloqueio de telefone

  - O comando a seguir habilita o bloqueio por telefone para o site Redmond. Para desativar o bloqueio de telefone, defina a propriedade EnforcePhoneLock como false ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>Para ativar o bloqueio de telefone e modificar o tempo limite do bloqueio do telefone

  - Esse comando ativa o bloqueio por telefone e também define o tempo limite do bloqueio do telefone como 30 minutos.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>Para habilitar o bloqueio de telefone em toda a organização

  - Neste exemplo, o bloqueio por telefone está habilitado em todas as configurações de configuração de telefone UC em uso na organização.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciando a autenticação do Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Gerenciando dispositivos, telefones e aplicativos do cliente no Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

