---
title: 'Lync Server 2013: configurar certificados para o diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for the Director
ms:assetid: 22988186-15ae-43b1-92f4-0adb3b75a7fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398296(v=OCS.15)
ms:contentKeyID: 48183612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d64eac2708c2b7fc1f0bfd3ab26a9bd38581f54c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-the-director-in-lync-server-2013"></a>Configurar certificados para o diretor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Ao executar o Assistente de certificado, certifique-se de que esteja conectado usando uma conta membro de um grupo com as permissões apropriadas para o tipo de modelo de certificado que será usado. Por padrão, uma solicitação de certificado do Lync Server 2013 usará o modelo de certificado do servidor Web. Se você usar uma conta membro do grupo RTCUniversalServerAdmins para solicitar um certificado usando esse modelo, verifique se o grupo recebeu as permissões Inscrever exigidas para usar esse modelo.



</div>

Cada Diretor requer um certificado padrão, um certificado da Web interno e um externo. Para obter detalhes sobre os requisitos de certificado para diretores, consulte [Certificate Requirements for Internal Servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) na documentação de planejamento.

Use o procedimento a seguir para configurar os certificados do diretor. Repita o procedimento para cada diretor. As etapas deste procedimento descrevem como configurar um certificado de uma autoridade de certificação raiz corporativa interna (AC) implantada pela sua organização e com o processamento de solicitação offline. Para obter detalhes sobre como obter certificados de uma autoridade de certificação externa, entre em contato com a equipe de suporte.

<div>

## <a name="to-configure-certificates-for-the-director-or-director-pool"></a>Para configurar certificados para o diretor ou pool de diretor

1.  No assistente de implantação do Lync Server, ao lado de **etapa 3: solicitar, instalar ou atribuir certificados**, clique em **executar**.

2.  Na página **Assistente de Certificados**, clique em **Solicitar**.

3.  Na página **Solicitação de Certificado**, clique em **Avançar**.

4.  Na página **solicitações atrasadas ou imediatas** , aceite a opção padrão **enviar a solicitação imediatamente para uma autoridade de certificação online** e clique em **Avançar**.

5.  Na página **escolher uma autoridade de certificação (CA)** , clique na autoridade de certificação interna do Windows que você deseja usar e clique em **Avançar**.

6.  Na página **conta da autoridade de certificação** , especifique as credenciais alternativas a serem usadas se a conta com a qual você está conectado não tiver autoridade suficiente para solicitar o certificado e clique em **Avançar**.

7.  Na página **Especificar Modelo de Certificado Alternativo**, clique em **Avançar**.

8.  Na página **nome e configurações de segurança** , é possível especificar um **nome amigável**, aceitar o comprimento da chave 2048 bits e clique em **Avançar**.

9.  Na página **Informações da Organização**, especifique, como opção, as informações da organização e clique em **Avançar**.

10. Na página **Informações Geográficas**, especifique, como opção, as informações geográficas e clique em **Avançar**.

11. Na página **nome do assunto/nomes alternativos da entidade** , clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > A lista de nomes alternativos da entidade deve conter o nome do computador no qual você está instalando o diretor (se um único diretor) ou o nome do pool de diretor e os nomes de URL simples configurados para a organização.

    
    </div>

12. Na página **configuração do domínio SIP em nomes alternativos da entidade (SANs)** , selecione os **domínios SIP configurados** para todos os domínios que você deseja que o diretor manipule e clique em **Avançar**.

13. Na página **Configurar Nomes Alternativos de Entidade Adicionais**, adicione quaisquer outros nomes alternativos de entidade necessários e clique em **Avançar**.

14. Na página **Resumo da Solicitação de Certificado**, clique em **Avançar**.

15. Na página **executando comandos** , clique em **Avançar** após a conclusão da execução dos comandos.

16. Na página **Status da Solicitação de Certificado Online**, clique em **Concluir**.

17. Na página **Atribuição de Certificado**, clique em **Avançar**.
    
    <div>
    

    > [!NOTE]  
    > Se você quiser exibir o certificado, clique duas vezes no certificado na lista.

    
    </div>

18. Na página **Resumo da Atribuição de Certificado**, clique em **Avançar**.

19. Na página **executando comandos** , clique em **concluir** após a conclusão da execução dos comandos.

20. Na página **Assistente de Certificado**, clique em **Fechar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

