---
title: 'Lync Server 2013: Configurar certificados do Diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d2da30923231087e706e2a969fdba2884361f6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>Configurar certificados do Diretor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Ao executar o assistente de certificado, certifique-se de que você esteja conectado usando uma conta que seja membro de um grupo que tenha recebido as permissões apropriadas para o tipo de modelo de certificado que você vai usar. Por padrão, uma solicitação de certificado do Lync Server 2013 usará o modelo de certificado de servidor Web. Se você usar uma conta que seja um membro do grupo RTCUniversalServerAdmins para solicitar um certificado usando esse modelo, verifique se o grupo recebeu as permissões de Registro necessárias para usar esse modelo.



</div>

Cada diretor requer um certificado padrão, um certificado interno da Web e um certificado externo da Web. Para obter detalhes sobre os requisitos de certificado para os directors, consulte [requisitos de certificado para servidores internos no Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) na documentação de planejamento.

Use o procedimento a seguir para configurar certificados de director. Repita o procedimento para cada diretor. As etapas deste procedimento descrevem como configurar um certificado de uma CA (autoridade de certificação) raiz corporativa interna implantada pela sua organização e com o processamento de solicitação offline. Para obter detalhes sobre como obter certificados de uma autoridade de certificação externa, entre em contato com a equipe de suporte.

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>Para configurar certificados para o diretor ou o pool do diretor

1.  No assistente de implantação do Lync Server, ao lado da **etapa 3: solicitar, instalar ou atribuir certificados**, clique em **executar**.

2.  Na página **Assistente de Certificados**, clique em **Solicitar**.

3.  Na página **solicitação de certificado** , clique em **Avançar**.

4.  Na página **solicitações atrasadas ou imediatas** , aceite o padrão **enviar a solicitação imediatamente para uma opção de autoridade de certificação online** e, em seguida, clique em **Avançar**.

5.  Na página **escolher uma CA (autoridade de certificação)** , clique na autoridade de certificação interna do Windows que você deseja usar e clique em **Avançar**.

6.  Na página da **conta da autoridade de certificação** , especifique as credenciais alternativas a serem usadas se a conta na qual você está conectado não tiver autoridade suficiente para solicitar o certificado e clique em **Avançar**.

7.  Na página **especificar modelo de certificado alternativo** , clique em **Avançar**.

8.  Na página **configurações de nome e segurança** , você pode especificar um **nome amigável**, aceitar o comprimento da chave de 2048 bits e, em seguida, clicar em **Avançar**.

9.  Na página **informações da organização** , especifique opcionalmente as informações da organização e clique em **Avançar**.

10. Na página **informações** geográficas, opcionalmente, especifique informações geográficas e clique em **Avançar**.

11. Na página **nome do assunto/nomes alternativos de assunto** , clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > A lista de nomes alternativos de entidades deve conter o nome do computador no qual você está instalando o diretor (se for um único diretor) ou o nome do pool de diretor e os nomes de URL simples configurados para a organização.

    
    </div>

12. Na **configuração de domínio SIP na página de nomes alternativos de entidades (SANs)** , selecione os **domínios SIP** configurados para todos os domínios que você deseja que o diretor manipule e clique em **Avançar**.

13. Na página **configurar nomes alternativos de entidades adicionais** , adicione os nomes alternativos de entidades adicionais necessários e clique em **Avançar**.

14. Na página **Resumo da solicitação de certificado** , clique em **Avançar**.

15. Na página **comandos em execução** , clique em **Avançar** depois que terminar a execução dos comandos.

16. Na página **status da solicitação de certificado online** , clique em **concluir**.

17. Na página **atribuição de certificado** , clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Se você quiser exibir o certificado, clique duas vezes no certificado na lista.

    
    </div>

18. Na página **Resumo de atribuição de certificado** , clique em **Avançar**.

19. Na página **comandos em execução** , clique em **concluir** após a conclusão da execução dos comandos.

20. Na página do **Assistente de certificado** , clique em **fechar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

