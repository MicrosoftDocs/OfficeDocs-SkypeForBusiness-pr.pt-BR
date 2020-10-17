---
title: Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bea847e1d0c4d9c42808a93f3c56bcd7391bece
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507158"
---
# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-05-14_

O Microsoft Lync Server 2013 deve ser capaz de se comunicar de forma segura e direta com outros produtos de servidor e aplicativos. Por exemplo, você pode configurar o Lync Server 2013 para que os dados de contato e/ou dados de arquivamento sejam armazenados no Microsoft Exchange Server 2013; no entanto, isso só poderá ser feito se o Lync Server e o Exchange puderem se comunicar com segurança uns com os outros. Da mesma forma, é possível agendar uma conferência do Lync Server a partir do Microsoft SharePoint Server; novamente, isso só poderá ser feito se dois servidores (SharePoint e Lync Server) confiarem um no outro. Embora seja possível usar um mecanismo de autenticação para a comunicação do Lync para o Exchange e um mecanismo separado para a comunicação do Lync para o SharePoint, uma abordagem melhor e mais eficiente é usar um método padronizado para todas as autenticações e autorizações de servidor para servidor.

O uso de um único método padronizado para autenticação de servidor para servidor é a abordagem realizada pelo Lync Server 2013. Para a versão 2013, o Lync Server 2013 (bem como outros produtos de servidor da Microsoft, incluindo o Exchange 2013 e o Microsoft SharePoint Server) dão suporte ao protocolo OAuth (autorização aberta) para autenticação e autorização de servidor para servidor. Com o OAuth, um protocolo de autorização padrão usado por vários dos sites principais, as credenciais e senhas do usuário não são passadas de um computador a outro. Em vez disso, a autenticação e autorização são baseadas na troca de tokens de segurança; esses tokens concedem acesso a um conjunto específico de recursos por um período determinado.

A autenticação com o OAuth geralmente envolve três partes: um servidor de autorização individual e dois realms que precisam se comunicar entre si. (Você também pode fazer a autenticação de servidor para servidor sem usar um servidor de autorização, um processo que será discutido posteriormente neste documento.) Os tokens de segurança são emitidos pelo servidor de autorização (também conhecido como servidor de token de segurança) para os dois territórios que precisam se comunicar; esses tokens verificam se as comunicações originárias de um realm devem ser confiáveis para o outro realm. Por exemplo, o servidor de autorização pode emitir tokens que verificam se os usuários de um território específico do Lync Server 2013 podem acessar um realm do Exchange 2013 especificado e vice-versa.

<div>


> [!NOTE]
> Um realm é simplesmente um contêiner de segurança. Por padrão, o Lync Server 2013 usa seu domínio SIP padrão como seu Realm OAuth. Namespaces SIP adicionais são adicionados à lista de nomes alternativos de entidade no certificado OAuth.



</div>

O Lync Server 2013 oferece suporte a três cenários de autenticação de servidor para servidor. Com o Lync Server 2013, você pode:

  - Configure a autenticação de servidor para servidor entre uma instalação local do Lync Server 2013 e uma instalação local do Exchange 2013 e/ou Microsoft SharePoint Server.

  - Configure a autenticação de servidor para servidor entre um par de componentes do Microsoft 365 (por exemplo, entre o Microsoft Exchange e o Microsoft Lync Server, ou entre o Microsoft Lync Server e o Microsoft SharePoint).

  - Configure a autenticação de servidor para servidor em um ambiente entre locais (ou seja, autenticação de servidor para servidor entre um servidor local e um componente do Microsoft 365).

Observe que, neste momento, somente o Exchange 2013, o SharePoint Server e o Lync Server 2013 dão suporte à autenticação de servidor para servidor; Se você não estiver executando um desses servidores, não poderá implementar completamente a autenticação OAuth.

Também deve ser indicado que você não precisa usar a autenticação de servidor para servidor: a autenticação de servidor para servidor não é necessária para implantar o Lync Server 2013. Se o Lync Server 2013 não precisar se comunicar com outros servidores (como o Exchange 2013), a autenticação de servidor para servidor não será necessária.

No entanto, a autenticação de servidor para servidor será exigida ser você quiser usar os novos recursos do Lync Server, como o "armazenamento de contato unificado". Com o repositório unificado de contatos, as informações de contato do Lync Server 2013 são armazenadas no Exchange 2013, e não no Lync Server; Isso permite que os usuários tenham um único conjunto de contatos prontamente acessível no Lync, no Microsoft Outlook ou no Microsoft Outlook Web Access. Como o repositório unificado de contatos requer o Lync Server 2013 para compartilhar informações com o Exchange 2013, você deve usar a autenticação de servidor para servidor a fim de implantar o recurso. A autenticação de servidor para servidor também é necessária se você optar por usar o arquivamento do Exchange, em que as transcrições de sessões de mensagens instantâneas são salvas como emails do Exchange 2013, e não como registros de banco de dados individuais.

Para a versão do Microsoft 365 do Lync Server para se comunicar com seu representante do Exchange, o Lync Server 2013 deve primeiro obter um token de segurança do servidor de autorização. O Lync Server usa o token de segurança para se identificar para o Exchange. A versão Microsoft 365 do Exchange deve passar pelo mesmo processo para se comunicar com o Lync Server 2013.

No entanto, para uma autenticação de servidor para servidor ente dois servidores da Microsoft, não é preciso usar um servidor de token terceirizado. Os produtos de servidor como o Lync Server 2013 e o Exchange 2013 têm um servidor token interno que pode ser usado para fins de autenticação com outros servidores da Microsoft (como o SharePoint Server) que dão suporte à autenticação de servidor para servidor. Por exemplo, o Lync Server 2013 pode ele mesmo gerar e assinar um token de segurança e usá-lo para se comunicar com o Exchange 2013. Em um caso como esse, não há a necessidade de um servidor de token terceirizado.

Para configurar a autenticação de servidor para servidor para uma implementação local do Lync Server 2013, você deve fazer duas coisas:

  - Atribuir um certificado ao emissor de token integrado do Lync Server.

  - Configure o servidor para o qual o Lync Server 2013 se comunicará como um "aplicativo de parceiro". Por exemplo, se o Lync Server 2013 precisa se comunicar com o Exchange 2013, será necessário configurar o Exchange para ser um aplicativo parceiro.

<div>


> [!NOTE]
> Um "aplicativo de parceiro" é qualquer aplicativo que o Lync Server 2013 possa trocar diretamente tokens de segurança com, sem precisar passar por um servidor de token de segurança de terceiros.



</div>

Observe que o OAuth é uma parte principal do produto e não pode ser desabilitado ou removido.

<div>

## <a name="see-also"></a>Confira também


[Atribuindo um certificado de autenticação de servidor para servidor ao Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[Configurando o Microsoft Lync Server 2013 em um ambiente entre locais](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

