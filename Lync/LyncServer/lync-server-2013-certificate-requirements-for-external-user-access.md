---
title: 'Lync Server 2013: requisitos de certificado para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7000456629a91742350b9866dc9e1441c18eee57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030865"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Requisitos de certificado para acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-03-29_

O software de comunicações do Microsoft Lync Server 2013 suporta o uso de um único certificado público para interfaces externas de borda de acesso e webconferência, além do serviço de autenticação A/V. A interface interna de Borda normalmente usa um certificado privado emitido por uma autoridade de certificação (CA) interna, mas também pode usar um certificado público, contanto que seja de uma CA pública confiável. O proxy reverso em sua implantação usa um certificado público e criptografa a comunicação do proxy reverso para os clientes e do proxy reverso para os servidores internos usando HTTP (ou seja, Segurança da camada de transporte sobre HTTP).

Veja a seguir os requisitos para o certificado público usado para interfaces externas de Borda de acesso e de webconferência e para o serviço de autenticação A/V:

  - O certificado precisa ser emitido por uma CA pública aprovada que suporta nomes de entidade alternativos. Para obter detalhes, consulte o artigo 929395 da base de dados de conhecimento da Microsoft, "parceiros de certificado de comunicações unificadas para o Exchange Server e o Communications Server" em [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).

  - Se o certificado for usado em um pool de Borda, ele deverá ser criado como exportável, com o mesmo certificado usado em cada Servidor de Borda no pool de Borda. O requisito de chave privada exportável serve para o serviço de Autenticação A/V, que precisa usar a mesma chave privada em todos os Servidores de Borda no pool.

  - Se você quiser maximizar o tempo de atividade para seus serviços de áudio/vídeo, revise os requisitos de certificado para implementar um certificado de serviço de borda A/V separado (ou seja, um certificado de serviço de borda A/V separado de outros fins de certificado de borda externa). Para obter detalhes, consulte [Changes in Lync server 2013 que afetam o planejamento do servidor de borda](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [planejar certificados do servidor de borda no Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) e [preparar certificados AV e OAuth no Lync Server 2013 usando-Reset-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).

  - O nome da entidade do certificado é o nome de domínio totalmente qualificado (FQDN) do serviço de borda de acesso ou VIP do balanceador de carga de hardware (por exemplo, access.contoso.com). ). O nome da entidade não pode ter um caractere curinga, deve ser um nome explícito.
    
    <div>
    

    > [!NOTE]  
    > Para o Lync Server 2013, isso não é mais um requisito, mas ainda é recomendado para compatibilidade com o Office Communications Server.

    
    </div>

  - A lista de nomes de entidade alternativos contém os FQDNs do seguinte:
    
      - A interface externa do serviço de borda de acesso ou VIP do balanceador de carga de hardware (por exemplo, sip.contoso.com).
        
        <div>
        

        > [!NOTE]  
        > Embora o nome de entidade do certificado seja igual ao FQDN da Borda de acesso, o nome de entidade alternativo também precisa conter o FQDN da Borda de acesso, pois a TLS ignora o nome de entidade e usa as entradas de nome de entidade alternativo para validação.

        
        </div>
    
      - Da interface externa da Borda de webconferência ou VIP do balanceador de carga de hardware (por exemplo, webcon.contoso.com).
    
      - Se você estiver usando a configuração ou federação automática de cliente, inclua também quaisquer FQDNs de domínio de SIP usados em sua empresa (por exemplo, sip.contoso.com, sip.fabrikam.com).
    
      - O serviço de borda A/V não usa as entradas de nome de entidade ou de nomes alternativos de entidade.
    
    <div>
    

    > [!NOTE]  
    > A ordem dos FQDNs na lista de nomes de entidade alternativos não importa.

    
    </div>

Se você estiver implantando múltiplos Servidores de Borda com carga balanceada em um site, o certificado do serviço de autenticação A/V instalado em cada Servidor de Borda deverá ser da mesma CA e deverá usar a mesma chave privada. Observe que a chave privada do certificado precisa ser exportável, independentemente se for usada em um Servidor de Borda ou em muitos Servidores de Borda. Também deve ser exportável se você solicitar o certificado de qualquer computador além do Servidor de Borda. Como o serviço de autenticação A/V não usa o nome de entidade ou o nome alternativo de entidade, é possível reutilizar o certificado de Borda de acesso contanto que os requisitos de nome de entidade e de nome de entidade alternativo sejam atendidos para a Borda de acesso e para a Borda de webconferência e a chave privada do certificado seja exportável.

Os requisitos para o certificado privado (ou público) usado na interface interna de Borda são os seguintes:

  - O certificado pode ser emitido por uma CA interna ou uma CA de certificado público aprovada.

  - O nome de entidade do certificado é normalmente o FQDN da interface interna da Borda ou o VIP do balanceador de carga de hardware (por exemplo, lsedge.contoso.com). No entanto, é possível usar um certificado curinga na Borda interna.

  - Nenhuma lista de nomes de entidade alternativos é necessária.

O proxy reverso em seus serviços de implantação solicitam:

  - Acesso de usuário externo para atender ao conteúdo das reuniões

  - Acesso de usuário externo para expandir e exibir membros dos grupos de distribuição

  - Acesso de usuário externo para arquivos baixáveis do Serviço de Catálogo de Endereços

  - Acesso de usuário externo ao cliente do Lync Web App

  - Acesso de usuário externo à página da web Configurações de Conferência Discada

  - Acesso de usuário externo ao Serviço de Informações de Local

  - Acesso de dispositivo externo ao Serviço de Atualização de Dispositivo e obtenção de atualizações

O proxy reverso publica as URLs de Componentes da web do servidor interno. As URLs dos componentes Web são definidas no diretor, servidor front-end ou pool de front-ends como **Serviços Web externos** no construtor de topologias.

Entradas curinga são suportadas no campo de nome de entidade alternativo do certificado atribuído ao proxy reverso. Para obter detalhes sobre como configurar a solicitação de certificado para o proxy reverso, consulte [solicitar e configurar um certificado para seu proxy http reverso no Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).

<div>

## <a name="see-also"></a>Confira também


[Suporte a certificados curinga no Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

