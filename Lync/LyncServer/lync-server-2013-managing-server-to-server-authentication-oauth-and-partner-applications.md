---
title: Gerenciamento de aplicativos de parceiros e autenticação de servidor para servidor (OAuth)
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
ms.openlocfilehash: 01de2856b8923fff76cf33dda7d7e6ba21889c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a>Gerenciamento de aplicativos de parceiros e autenticação de servidor para servidor (OAuth) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-05-14_

O Microsoft Lync Server 2013 deve ser capaz de ser seguro e perfeitamente, comunicar-se com outros aplicativos e produtos de servidor. Por exemplo, você pode configurar o Lync Server 2013 para que os dados de contato e/ou arquivamento de dados sejam armazenados no Microsoft Exchange Server 2013; no entanto, isso pode ser feito apenas se o Lync Server e o Exchange puderem se comunicar com segurança uns com os outros. Da mesma forma, você pode agendar uma conferência do Lync Server no Microsoft SharePoint Server; novamente, no entanto, isso só poderá ser feito se os dois servidores (SharePoint e Lync Server) confiarem um ao outro. Embora seja possível usar um mecanismo de autenticação para a comunicação do Lync para o Exchange e um mecanismo separado para a comunicação do Lync para o SharePoint, uma abordagem melhor e mais eficiente é usar um método padronizado para todos os servidores autenticação e autorização.

Usar um único método padronizado para autenticação de servidor para servidor é a abordagem adotada pelo Lync Server 2013. Para a versão do 2013, o Lync Server 2013 (bem como outros produtos do Microsoft Server, incluindo Exchange 2013 e Microsoft SharePoint Server) dão suporte ao protocolo OAuth (autorização aberta) para autenticação e autorização do servidor para servidor. Com o OAuth, um protocolo de autorização padrão usado por vários dos sites principais, as credenciais e senhas do usuário não são passadas de um computador a outro. Em vez disso, a autenticação e autorização são baseadas na troca de tokens de segurança; esses tokens concedem acesso a um conjunto específico de recursos por um período determinado.

A autenticação com o OAuth geralmente envolve três partes: um servidor de autorização individual e dois realms que precisam se comunicar entre si. (Você também pode fazer a autenticação de servidor para servidor sem usar um servidor de autorização, um processo que será discutido posteriormente neste documento.) Os tokens de segurança são emitidos pelo servidor de autorização (também conhecido como um servidor de token de segurança) para os dois territórios que precisam se comunicar; esses tokens verificam se as comunicações que se originam de um território devem ser confiadas pelo outro território. Por exemplo, o servidor de autorização pode emitir tokens que verificam se os usuários de um território específico do Lync Server 2013 podem acessar um território especificado do Exchange 2013 e vice-versa.

<div>


> [!NOTE]
> Um realm é simplesmente um contêiner de segurança. Por padrão, o Lync Server 2013 usa o seu domínio SIP padrão como seu território OAuth. Namespaces SIP adicionais são adicionadas à lista Nome Alternativo da Entidade no certificado OAuth.



</div>

O Lync Server 2013 dá suporte a três cenários de autenticação de servidor para servidor. Com o Lync Server 2013, você pode:

  - Configurar a autenticação de servidor para servidor entre uma instalação local do Lync Server 2013 e uma instalação local do Exchange 2013 e/ou Microsoft SharePoint Server.

  - Configurar a autenticação de servidor para servidor entre um par de componentes do Office 365 (por exemplo, entre o Microsoft Exchange e o Microsoft Lync Server ou entre o Microsoft Lync Server e o Microsoft SharePoint).

  - Configurar a autenticação de servidor para servidor em um ambiente de várias instalações (ou seja, autenticação de servidor para servidor entre um servidor local e um componente do Office 365).

Observe que, nesse momento, somente o Exchange 2013, o SharePoint Server e o Lync Server 2013 dão suporte à autenticação de servidor para servidor; Se você não estiver executando um desses servidores, não será possível implementar completamente a autenticação OAuth.

Também deve ser indicado que você não precisa usar a autenticação de servidor para servidor: a autenticação de servidor para servidor não é necessária para implantar o Lync Server 2013. Se o Lync Server 2013 não precisar se comunicar com outros servidores (como o Exchange 2013), a autenticação de servidor para servidor não será necessária.

No entanto, a autenticação de servidor para servidor será necessária se você quiser usar alguns dos novos recursos do Lync Server, como o "repositório de contatos unificado". Com o repositório de contatos unificado, as informações de contato do Lync Server 2013 são armazenadas no Exchange 2013 em vez de no Lync Server; Isso permite que os usuários tenham um único conjunto de contatos que seja facilmente acessível no Lync, Microsoft Outlook ou Microsoft Outlook Web Access. Como o repositório de contatos unificado requer o Lync Server 2013 para compartilhar informações com o Exchange 2013, você deve usar a autenticação de servidor para servidor para implantar o recurso. A autenticação de servidor para servidor também será necessária se você optar por usar o arquivamento do Exchange, no qual as transcrições de sessões de mensagens instantâneas são salvas como emails do Exchange 2013 em vez de registros de banco de dados individuais.

Para que a versão do Office 365 do Lync Server se comunique com sua contraparte do Exchange, o Lync Server 2013 deve primeiro obter um token de segurança do servidor de autorização. Em seguida, o Lync Server usa o token de segurança para se identificar para o Exchange. A versão do Office 365 do Exchange deve passar pelo mesmo processo a fim de se comunicar com o Lync Server 2013.

No entanto, para uma autenticação de servidor para servidor ente dois servidores da Microsoft, não é preciso usar um servidor de token terceirizado. Os produtos de servidor como o Lync Server 2013 e o Exchange 2013 têm um servidor de token interno que pode ser usado para fins de autenticação com outros servidores da Microsoft (como o SharePoint Server) que dão suporte à autenticação de servidor para servidor. Por exemplo, o Lync Server 2013 pode emitir e assinar um token de segurança por si só e, em seguida, usar esse token para se comunicar com o Exchange 2013. Em um caso como esse, não há a necessidade de um servidor de token terceirizado.

Para configurar a autenticação de servidor para servidor para uma implementação local do Lync Server 2013, você deve fazer duas coisas:

  - Atribuir um certificado ao emissor de token interno do Lync Server.

  - Configure o servidor no qual o Lync Server 2013 se comunicará como um "aplicativo parceiro". Por exemplo, se o Lync Server 2013 precisar se comunicar com o Exchange 2013, será necessário configurar o Exchange para ser um aplicativo de parceiro.

<div>


> [!NOTE]
> Um "aplicativo de parceiro" é qualquer aplicativo no qual o Lync Server 2013 possa trocar diretamente tokens de segurança com, sem precisar passar por um servidor de token de segurança de terceiros.



</div>

Observe que o OAuth é uma parte essencial do produto e não pode ser desabilitado, nem removido.

<div>

## <a name="see-also"></a>Confira também


[Atribuindo um certificado de autenticação de servidor a servidor ao Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[Configurando o Microsoft Lync Server 2013 em um ambiente de várias instalações](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

