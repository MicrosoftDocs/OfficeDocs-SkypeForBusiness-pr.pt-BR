---
title: 'Lync Server 2013: Usando o portal administrativo da Web do Sistema de Salas do Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c891309d76dda20f875592841925c852fe2e3351
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Usando o portal administrativo da Web do Sistema de Salas do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-11-10_

Depois de implantar o LRS no servidor, você pode verificar o status de todas as salas LRS conectando-se ao portal da Web administrativo do LRS a partir de um navegador.

<div>

## <a name="sign-in"></a>Entrar

1.  Acesse a seguinte URL:
    
    https://\<FE-servidor\>/lRS

2.  Insira as credenciais para a conta LRSSupport ou uma conta que foi adicionada ao grupo de segurança LRSSupportAdminGroup.

![Tela de entrada do portal de administração do sistema de salas do Lync](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Tela de entrada do portal de administração do sistema de salas do Lync")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>Página de resumo do portal da Web administrativo do LRS

A página Resumo fornece as seguintes informações para todas as salas LRS implantadas no servidor:

  - **Marque**   o nome personalizado que o administrador fornece à sala. A marca pode ser definida no portal clicando no nome da sala.

  - **Integridade**   o status de integridade da sala, que é derivado do status de integridade da agregação da sala, que é mostrado na seção integridade da página de configurações da sala.

  - **Próxima reunião**   a data e a hora em que a próxima reunião está agendada.

  - **LRS versão, fabricante, modelo**   esses valores são predefinidos em lRS. Dependendo do fabricante, esses campos podem ser deixados em branco.

  - **Última atualização**   exibe a última vez que a página da Web foi atualizada.

![Exibição resumida do portal de administração do sistema de salas do Lync](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Exibição resumida do portal de administração do sistema de salas do Lync")

</div>

<div>

## <a name="lrs-room-information"></a>Informações da sala de LRS

A seção informações da sala do portal permite que você visualize e configure salas individuais do LRS. Ele contém quatro seções: configurações, detalhes, solução de problemas e integridade.

<div>

## <a name="settings"></a>Configurações

Na seção Configurações, você pode definir a senha, a marca de sala e os níveis de volume padrão da sala. Se você definir essas configurações, as alterações serão replicadas apenas depois que você reiniciar o console do LRS. Você só verá as configurações de atualizações do sistema para sistemas de sala do Lync, versão 15,12 e posteriores.

![Configurações da sala do portal de administração do sistema de salas do Lync](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Configurações da sala do portal de administração do sistema de salas do Lync")

</div>

<div>

## <a name="details"></a>Detalhes

A seção detalhes fornece um resumo somente leitura das configurações da sala de LRS, incluindo: o tempo da última atualização; próxima reunião; últimas atualizações, manutenção e calibragem; configurações de alto-falante, microfone e toque padrão; versões URI SIP; número de telas e detalhes sobre cada tela; status e atividade.

![Visão detalhada do portal de administração do sistema de salas do Lync](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Visão detalhada do portal de administração do sistema de salas do Lync")

</div>

<div>

## <a name="troubleshooting"></a>Solução de problemas

A seção solução de problemas pode ser usada para coletar logs remotamente e salvá-los em um local específico. Você também pode reiniciar o console do LRS (LRS user interface) ou reiniciar o sistema inteiro. Para coletar logs, forneça um caminho de pasta no formato especificado e certifique-se de que a pasta tenha permissões de gravação atribuídas à conta de computador LRS. Se o tamanho do log for muito grande, pode levar até 5 minutos para concluir a coleta de logs. A atualização da página dará o status mais recente.

![Log de sala do portal de administração do sistema de salas do Lync](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Log de sala do portal de administração do sistema de salas do Lync")

</div>

<div>

## <a name="health"></a>Geral

A seção integridade fornece uma indicação visual da integridade da conexão do Lync Server, do dispositivo de áudio, do dispositivo de vídeo, do estado de resiliência e do dispositivo de tela.

![Portal de administração do Lync System da sala integridade](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Portal de administração do Lync System da sala integridade")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>Anotações adicionais sobre o portal administrativo da Web

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>As alterações de configuração são aplicadas somente após a reinicialização do sistema do LRS.</P>
> <LI>
> <P>Se a senha da conta do LRSApp expirar, você não poderá ver o status das salas. Configure a senha da conta do LRSAppuser para que ela nunca expire ou atualize a senha quando ela estiver próxima de expiração.</P>
> <LI>
> <P>O portal da Web administrativo do LRS tem suporte para implantações locais apenas.</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>Perguntas frequentes

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Por que não consigo me conectar ao portal administrativo da Web?

  - Ao abrir https://localhost/lrs, você poderá ver a página de entrada, mas quando digitar as suas credenciais, não poderá se conectar. Nesse caso, você deve abrir https://FQDNofFEserver/lrs para entrar no portal administrativo da Web.

  - Se a máquina a partir da qual você está acessando o portal da Web administrativo estiver em um grupo de trabalho, "http://" não funcionará. Em vez disso, use "https".

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>Por que não consigo ver o LRS no portal da Web administrativo?

  - Verifique se você tem contas do LRS em sua implantação e se elas são criadas de acordo com as recomendações de implantação do portal de Web administrativo do LRS. Certifique-se de que as contas do LRS sejam provisionadas usando enable-CsMeetingRoom, not Enable-CsUser, no servidor do Lync.

  - Se você criou contas do LRS e não consegue ver as contas no portal administrativo da Web, colete os logs do servidor usando a ferramenta de log do Lync Server com o componente **MeetingPortal** selecionado e, em seguida, envie-os para o contato do lRS support.

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>Por que não consigo ver o status do LRS no portal da Web administrativo?

  - Certifique-se de que a conta de usuário do LRSApp seja compatível com SIP.

  - Se ainda estiver com problemas, colete o arquivo **trace. log** no sistema LRS de D:\\rastreamento\\LRSAdminLogs\\e, em seguida, envie-o para o seu contato do lRS support.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

