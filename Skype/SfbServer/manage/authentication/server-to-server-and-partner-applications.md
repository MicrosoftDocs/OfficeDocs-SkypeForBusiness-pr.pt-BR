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
description: 'Resumo: gerenciar aplicativos OAuth e de parceiros no Skype for Business Server.'
ms.openlocfilehash: d95d4f048743c6725e42e50b5025b0c906adaf53
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818743"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Skype for Business Server
 
**Resumo:** Gerenciar aplicativos OAuth e de parceiros no Skype for Business Server.
  
O Skype for Business Server deve ser capaz de ser seguro e perfeitamente, comunicar-se com outros aplicativos e produtos de servidor. Por exemplo, você pode configurar o Skype for Business Server para que os dados de contato e/ou arquivamento de dados sejam armazenados no Microsoft Exchange Server 2013; no entanto, isso pode ser feito apenas se o Skype for Business Server e o Exchange puderem se comunicar com segurança uns com os outros. Da mesma forma, você pode agendar uma conferência do Skype for Business Server em um servidor do Office Web Apps; novamente, isso só poderá ser feito se os dois servidores (SharePoint e Skype for Business Server) confiarem uns aos outros. Embora seja possível usar um mecanismo de autenticação para comunicação entre o Skype for Business Server e o Exchange, mas um mecanismo separado para o Skype for Business Server e a comunicação do SharePoint, uma abordagem melhor e mais eficiente é usar um método padronizado para toda a autorização e autenticação entre servidores.
  
Usar um único método padronizado para autenticação de servidor para servidor é a abordagem adotada pelo Skype for Business Server. Iniciado com o Office Servers versão 2013, o Skype for Business Server (bem como outros produtos do Microsoft Server, incluindo o Exchange Server e o SharePoint Server) suportavam o protocolo OAuth (autorização aberta) para autenticação de servidor para servidor e baseado. Com o OAuth, um protocolo de autorização padrão usado por vários dos sites principais, as credenciais e senhas do usuário não são passadas de um computador a outro. Em vez disso, a autenticação e autorização são baseadas na troca de tokens de segurança; esses tokens concedem acesso a um conjunto específico de recursos por um período determinado.
  
A autenticação com o OAuth geralmente envolve três partes: um servidor de autorização individual e dois realms que precisam se comunicar entre si. (Você também pode fazer a autenticação de servidor para servidor sem usar um servidor de autorização, um processo que será discutido posteriormente neste documento.) Os tokens de segurança são emitidos pelo servidor de autorização (também conhecido como um servidor de token de segurança) para os dois territórios que precisam se comunicar; esses tokens verificam se as comunicações que se originam de um território devem ser confiadas pelo outro território. Por exemplo, o servidor de autorização pode emitir tokens que verificam se os usuários de um território específico do Skype for Business são capazes de acessar um território do Exchange especificado, e vice-versa.
  
> [!NOTE]
> Um realm é simplesmente um contêiner de segurança. Por padrão, o Skype for Business Server usa o seu domínio SIP padrão como seu território OAuth. Namespaces SIP adicionais são adicionadas à lista Nome Alternativo da Entidade no certificado OAuth. 
  
O Skype for Business Server oferece suporte a três cenários de autenticação entre servidores. Com o Skype for Business Server, você pode:
  
- Configurar a autenticação de servidor para servidor entre uma instalação local do Skype for Business Server e uma instalação local do Exchange e/ou do SharePoint Server.
    
- Configurar a autenticação de servidor para servidor entre um par de componentes do Office 365 (por exemplo, entre o Microsoft Exchange Server e o Skype for Business Server ou entre o Skype for Business Server e o SharePoint).
    
- Configurar a autenticação de servidor para servidor em um ambiente de várias instalações (ou seja, autenticação de servidor para servidor entre um servidor local e um componente do Office 365).
    
Observe que, nesse momento, somente o Exchange 2013, o SharePoint Server, o Lync Server 2013, o Skype for Business Server 2015 e o Skype for Business 2019 dão suporte à autenticação de servidor para servidor; Se você não estiver executando um desses servidores, não poderá implementar completamente a autenticação OAuth.
  
Também deve ser indicado que a autenticação servidor-a-servidor é opcional: se o Skype for Business Server não precisar se comunicar com outros servidores (como o Exchange), a autenticação de servidor para servidor pode ser totalmente ignorada. Se a autenticação de servidor para servidor já estiver configurada para o Lync Server 2013 e outros aplicativos, não será necessário fazê-lo novamente para o Skype for Business Server. 
  
No entanto, a autenticação de servidor para servidor será necessária se você quiser usar alguns dos recursos do Skype for Business Server, como o "repositório de contatos unificado". Com o repositório de contatos unificado, as informações de contato do Skype for Business Server são armazenadas no Exchange, e não no Skype for Business Server; Isso permite que os usuários tenham um único conjunto de contatos que está prontamente acessível no Skype for Business, no Outlook ou no Outlook Web Access. Como o repositório de contatos unificado requer o Skype for Business Server para compartilhar informações com o Exchange, você deve usar a autenticação de servidor para servidor a fim de implantar o recurso. A autenticação de servidor para servidor também será necessária se você optar por usar o arquivamento do Exchange, no qual as transcrições de sessões de mensagens instantâneas são salvas como emails do Exchange, em vez de registros de banco de dados individuais.
  
Para que a versão do Office 365 do Skype for Business Server se comunique com sua contraparte do Exchange, o Skype for Business Server deve primeiro obter um token de segurança do servidor de autorização. O Skype for Business Server usa o token de segurança para se identificar para o Exchange. A versão do Office 365 do Exchange deve passar pelo mesmo processo a fim de se comunicar com o Skype for Business Server.
  
No entanto, para uma autenticação de servidor para servidor ente dois servidores da Microsoft, não é preciso usar um servidor de token terceirizado. Os produtos de servidor como o Skype for Business Server e o Exchange têm um servidor de token interno que pode ser usado para fins de autenticação com outros servidores da Microsoft (como o SharePoint Server) que dão suporte à autenticação de servidor para servidor. Por exemplo, o Skype for Business Server pode emitir e assinar um token de segurança por conta própria e usar esse token para se comunicar com o Exchange. Em um caso como esse, não há a necessidade de um servidor de token terceirizado.
  
Para configurar a autenticação de servidor para servidor para uma implementação local do Skype for Business Server, você deve fazer duas coisas:
  
- Atribua um certificado ao emissor de token interno do Skype for Business Server.
    
- Configure o servidor com o qual o Skype for Business Server se comunicará como "aplicativo parceiro". Por exemplo, se o Skype for Business Server precisar se comunicar com o Exchange, será necessário configurar o Exchange para ser um aplicativo de parceiro.
    
> [!NOTE]
> Um "aplicativo de parceiro" é qualquer aplicativo no qual o Skype for Business Server possa trocar diretamente tokens de segurança com, sem precisar passar por um servidor de token de segurança de terceiros. 
  
Observe que o OAuth é uma parte essencial do produto e não pode ser desabilitado, nem removido.
  
## <a name="see-also"></a>Confira também

[Atribuir um certificado de autenticação de servidor a servidor ao Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[Configurar um ambiente híbrido no Skype for Business Server](configure-a-hybrid-environment.md)
