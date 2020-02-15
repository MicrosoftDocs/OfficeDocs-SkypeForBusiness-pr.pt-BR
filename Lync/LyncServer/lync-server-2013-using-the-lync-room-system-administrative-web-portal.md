---
title: 'Lync Server 2013: usando o portal da Web administrativo do sistema de salas do Lync'
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
ms.openlocfilehash: 3871002fc07c0129c1caa2cb6b86734548b20a66
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Usando o portal da Web administrativo do sistema de salas do Lync no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-11-10_

Depois de implantar o LRS no servidor, você pode verificar o status de todas as salas do LRS entrando no portal da Web administrativo do LRS a partir de um navegador.

<div>

## <a name="sign-in"></a>Entrar

1.  Navegue até a seguinte URL:
    
    https://\<FE-servidor\>/lRS

2.  Insira as credenciais para a conta LRSSupport ou uma conta que tenha sido adicionada ao grupo de segurança LRSSupportAdminGroup.

![Tela de entrada do portal de administração do sistema de salas do Lync](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Tela de entrada do portal de administração do sistema de salas do Lync")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>Página de resumo do portal Web administrativo do LRS

A página de resumo fornece as seguintes informações para todas as salas do LRS implantadas no servidor:

  - **Marca**   o nome personalizado que o administrador fornece à sala. A marca pode ser definida no portal clicando no nome da sala.

  - **Integridade**   o status de integridade da sala, que é derivado do status de integridade de agregação da sala, que é mostrado na seção integridade da página Configurações da sala.

  - **Próxima reunião**   a data e a hora em que a próxima reunião foi agendada.

  - **Versão lRS, fabricante, modelo**   esses valores são predefinidos no lRS. Dependendo do fabricante, esses campos podem ser deixados em branco.

  - **Última atualização**   exibe a última vez que a página da Web foi atualizada.

![Exibição resumida do portal de administração do sistema de salas do Lync](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Exibição resumida do portal de administração do sistema de salas do Lync")

</div>

<div>

## <a name="lrs-room-information"></a>Informações de sala do LRS

A seção informações de sala do portal permite que você visualize e configure salas individuais do LRS. Ele contém quatro seções: configurações, detalhes, solução de problemas e integridade.

<div>

## <a name="settings"></a>Configurações

Na seção Configurações, é possível definir a senha, a marca de sala e os níveis de volume padrão para a sala. Se você definir essas configurações, as alterações serão replicadas somente depois que o console do LRS for reiniciado. Você verá apenas as configurações de atualizações do sistema para sistemas de salas do Lync que são a versão 15,12 e posterior.

![Configurações de sala do portal de administração do sistema de salas do Lync](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Configurações de sala do portal de administração do sistema de salas do Lync")

</div>

<div>

## <a name="details"></a>Detalhes

A seção detalhes fornece um resumo somente leitura das configurações da sala de LRS, incluindo: o horário da última atualização; próxima reunião; últimas atualizações, manutenção e calibração; configurações de alto-falante, MIC e campainha padrão; Version URI DO SIP; número de telas e detalhes sobre cada tela; status e atividade.

![Exibição detalhada do portal de administração do sistema de salas do Lync](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Exibição detalhada do portal de administração do sistema de salas do Lync")

</div>

<div>

## <a name="troubleshooting"></a>Solução de problemas

A seção solução de problemas pode ser usada para coletar logs remotamente e salvá-los em um local especificado. Também é possível reiniciar o console do LRS (LRS user interface) ou reiniciar todo o sistema. Para coletar logs, forneça um caminho de pasta no formato especificado e certifique-se de que a pasta tenha permissões de gravação atribuídas à conta de máquina do LRS. Se o tamanho do log for muito grande, pode levar até 5 minutos para concluir a coleta de logs. A atualização da página fornecerá o status mais recente.

![Log de sala do portal de administração do sistema de salas do Lync](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Log de sala do portal de administração do sistema de salas do Lync")

</div>

<div>

## <a name="health"></a>Integridade

A seção integridade fornece uma indicação visual da integridade da conexão do Lync Server, dispositivo de áudio, dispositivo de vídeo, estado de resiliência e dispositivo de tela.

![Integridade da sala do portal de administração do sistema de salas do Lync](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Integridade da sala do portal de administração do sistema de salas do Lync")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>Observações adicionais sobre o portal da Web administrativo

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>As alterações de configuração são aplicadas somente após a reinicialização do sistema do LRS.</P>
> <LI>
> <P>Se a senha da conta LRSApp expirar, você não poderá ver o status das salas. Configure a senha da conta LRSAppuser para que ela nunca expire ou atualize a senha quando estiver próxima de expirar.</P>
> <LI>
> <P>O portal da Web administrativo do LRS tem suporte apenas para implantações locais.</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>Perguntas Frequentes

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Por que não consigo entrar no portal da Web administrativo?

  - Ao abrir https://localhost/lrso, você poderá ver a página de entrada, mas quando digitar suas credenciais, não poderá entrar. Nesse caso, você deve abrir https://FQDNofFEserver/lrs o para entrar no portal da Web administrativo.

  - Se o computador a partir do qual você está acessando o portal da Web administrativo estiver em um grupo de trabalho, "http://" não funcionará. Em vez disso, use "https".

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>Por que não consigo ver LRS no portal da Web administrativo?

  - Verifique se você tem contas do LRS em sua implantação e se elas foram criadas de acordo com as recomendações de implantação do portal da Web administrativo do LRS. Certifique-se de que as contas do LRS são provisionadas usando enable-CsMeetingRoom, não Enable-CsUser, no Lync Server.

  - Se você tiver criado contas do LRS e não puder ver as contas no portal da Web administrativo, colete os logs do servidor usando a ferramenta de registro em log do Lync Server com o componente **MeetingPortal** selecionado e, em seguida, envie-os para o contato de suporte do lRS.

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>Por que não consigo ver o status do LRS no portal da Web administrativo?

  - Verifique se a conta de usuário LRSApp está habilitada para SIP.

  - Se você ainda estiver tendo problemas, colete o arquivo **trace. log** no sistema LRS de D:\\rastreamento\\LRSAdminLogs\\e envie-o para o seu contato de suporte do lRS.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

