---
title: Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Resumo: gerenciar aplicativos OAuth e parceiros no Skype for Business Server.'
ms.openlocfilehash: f784dd0a2dab05fb3b97497fab7d3866dda1a753
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221665"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Skype for Business Server
 
**Resumo:** Gerenciar aplicativos OAuth e de parceiros no Skype for Business Server.
  
O Skype for Business Server deve ser capaz de se comunicar de forma segura e direta com outros produtos de servidor e aplicativos. Por exemplo, você pode configurar o Skype for Business Server para que os dados de contato e/ou dados de arquivamento sejam armazenados no Microsoft Exchange Server 2013; no entanto, isso só poderá ser feito se o Skype for Business Server e o Exchange puderem se comunicar com segurança uns com os outros. Da mesma forma, você pode agendar uma conferência do Skype for Business Server de dentro do servidor do Office Web Apps; novamente, isso só poderá ser feito se os dois servidores (SharePoint e Skype for Business Server) confiar um no outro. Embora seja possível usar um mecanismo de autenticação para comunicação entre o Skype for Business Server e o Exchange, mas um mecanismo separado para o Skype for Business Server e a comunicação do SharePoint, uma abordagem melhor e mais eficiente é usar um método padronizado para todas as autenticações e autorização de servidor para servidor.
  
O uso de um único método padronizado para autenticação de servidor para servidor é a abordagem realizada pelo Skype for Business Server. Iniciado com os servidores do Office versão 2013, o Skype for Business Server (bem como outros produtos de servidor da Microsoft, incluindo o Exchange Server e o SharePoint Server) oferece suporte ao protocolo OAuth (Open Authorization) para autenticação e autorização de servidor para servidor. Com o OAuth, um protocolo de autorização padrão usado por vários dos sites principais, as credenciais e senhas do usuário não são passadas de um computador a outro. Em vez disso, a autenticação e autorização são baseadas na troca de tokens de segurança; esses tokens concedem acesso a um conjunto específico de recursos por um período determinado.
  
A autenticação com o OAuth geralmente envolve três partes: um servidor de autorização individual e dois realms que precisam se comunicar entre si. (Você também pode fazer a autenticação de servidor para servidor sem usar um servidor de autorização, um processo que será discutido posteriormente neste documento.) Os tokens de segurança são emitidos pelo servidor de autorização (também conhecido como servidor de token de segurança) para os dois territórios que precisam se comunicar; esses tokens verificam se as comunicações originárias de um realm devem ser confiáveis para o outro realm. Por exemplo, o servidor de autorização pode emitir tokens que verificam se os usuários de um realm do Skype for Business Server podem acessar um realm do Exchange específico e vice-versa.
  
> [!NOTE]
> Um realm é simplesmente um contêiner de segurança. Por padrão, o Skype for Business Server usa seu domínio SIP padrão como seu Realm OAuth. Namespaces SIP adicionais são adicionados à lista de nomes alternativos de entidade no certificado OAuth. 
  
O Skype for Business Server oferece suporte a três cenários de autenticação de servidor para servidor. Com o Skype for Business Server, você pode:
  
- Configure a autenticação de servidor para servidor entre uma instalação local do Skype for Business Server e uma instalação local do Exchange e/ou do SharePoint Server.
    
- Configure a autenticação de servidor para servidor entre um par de componentes do Microsoft 365 ou do Office 365 (por exemplo, entre o Microsoft Exchange Server e o Skype for Business Server ou entre o Skype for Business Server e o SharePoint).
    
- Configure a autenticação de servidor para servidor em um ambiente entre locais (ou seja, autenticação de servidor para servidor entre um servidor local e um componente do Microsoft 365 ou do Office 365).
    
Observe que, neste momento, somente o Exchange 2013, o SharePoint Server, o Lync Server 2013, o Skype for Business Server 2015 e o Skype for Business 2019 dão suporte à autenticação de servidor para servidor; Se você não estiver executando um desses servidores, você não poderá implementar completamente a autenticação OAuth.
  
Também deve ser indicado que a autenticação de servidor para servidor é opcional: se o Skype for Business Server não precisa se comunicar com outros servidores (como o Exchange), a autenticação de servidor para servidor pode ser totalmente ignorada. Se a autenticação de servidor para servidor já estiver configurada para o Lync Server 2013 e outros aplicativos, não será necessário fazê-lo novamente para o Skype for Business Server. 
  
No entanto, a autenticação de servidor para servidor é necessária se você deseja usar alguns dos recursos no Skype for Business Server, como o "repositório unificado de contatos". Com o repositório unificado de contatos, as informações de contato do Skype for Business Server são armazenadas no Exchange, e não no Skype for Business Server; Isso permite que os usuários tenham um único conjunto de contatos prontamente acessível no Skype for Business, Outlook ou Outlook Web Access. Como o repositório unificado de contatos requer o Skype for Business Server para compartilhar informações com o Exchange, você deve usar a autenticação de servidor para servidor a fim de implantar o recurso. A autenticação de servidor para servidor também é necessária se você optar por usar o arquivamento do Exchange, em que as transcrições de sessões de mensagens instantâneas são salvas como emails do Exchange, e não como registros de banco de dados individuais.
  
Para que a versão do Microsoft 365 ou do Office 365 do Skype for Business Server se comunique com seu representante do Exchange, o Skype for Business Server deve primeiro obter um token de segurança do servidor de autorização. O Skype for Business Server usa o token de segurança para se identificar para o Exchange. As versões do Microsoft 365 ou do Office 365 do Exchange devem passar pelo mesmo processo para se comunicar com o Skype for Business Server.
  
No entanto, para uma autenticação de servidor para servidor ente dois servidores da Microsoft, não é preciso usar um servidor de token terceirizado. Produtos de servidor como o Skype for Business Server e o Exchange têm um servidor de token interno que pode ser usado para fins de autenticação com outros servidores da Microsoft (como o SharePoint Server) que dão suporte à autenticação de servidor para servidor. Por exemplo, o Skype for Business Server pode emitir e assinar um token de segurança sozinho e, em seguida, usar esse token para se comunicar com o Exchange. Em um caso como esse, não há a necessidade de um servidor de token terceirizado.
  
Para configurar a autenticação de servidor para servidor para uma implementação local do Skype for Business Server, você deve fazer duas coisas:
  
- Atribuir um certificado ao emissor de token interno do Skype for Business Server.
    
- Configure o servidor com o qual o Skype for Business Server se comunicará como "aplicativo parceiro". Por exemplo, se o Skype for Business Server precisa se comunicar com o Exchange, será necessário configurar o Exchange para ser um aplicativo parceiro.
    
> [!NOTE]
> Um "aplicativo de parceiro" é qualquer aplicativo que o Skype for Business Server possa trocar diretamente com tokens de segurança, sem precisar passar por um servidor de token de segurança de terceiros. 
  
Observe que o OAuth é uma parte principal do produto e não pode ser desabilitado ou removido.
  
## <a name="see-also"></a>Confira também

[Atribuir um certificado de autenticação de servidor para servidor ao Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[Configurar um ambiente híbrido no Skype for Business Server](configure-a-hybrid-environment.md)
