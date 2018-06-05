---
title: Gerenciar autenticação de servidor para servidor (Oauth) e inscrições de parceiros no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Resumo: Gerencie os aplicativos de OAuth e parceiros em Skype para Business Server 2015.'
ms.openlocfilehash: acbc8cfa9fd43bdc73752278d1da805d5b4a31ef
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504394"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server-2015"></a>Gerenciar autenticação de servidor para servidor (Oauth) e inscrições de parceiros no Skype for Business Server 2015
 
**Resumo:** Gerencie aplicativos de OAuth e parceiros em Skype para Business Server 2015.
  
Skype para Business Server 2015 deve ser capaz de forma segura e perfeitamente, se comunicar com outros aplicativos e produtos de servidor. Por exemplo, você pode configurar Skype para Business Server 2015 forma que contato dados e/ou dados de arquivamento são armazenados no Microsoft Exchange Server 2013; No entanto, isso só pode ser feito se Skype para Business Server e do Exchange é capaz de se comunicar umas com as outras de segurança. Da mesma forma, você pode agendar uma Skype para conferência de Business Server de dentro do Office Web Apps Server; novamente, isso só pode ser feito se os dois servidores (SharePoint e Skype para Business Server) confiem uns nos outros. Embora seja possível usar um mecanismo de autenticação para comunicação entre o Skype para Business Server e do Exchange, mas um mecanismo separado para Skype para comunicação Business Server e do SharePoint, uma abordagem melhor e mais eficiente é usar um método padronizado para todos os servidor-para-servidor autenticação e autorização.
  
Usando uma única, o método padronizado para autenticação de servidor-para-servidor é a abordagem tomada pelo Skype para Business Server 2015. Para o 2013 release, Skype para Business Server 2015 (assim como outros produtos Microsoft Server, incluindo o Exchange 2013 e SharePoint Server) oferecem suporte ao protocolo de OAuth (Open Authorization) para autenticação de servidor-para-servidor e autorização. Com o OAuth, um protocolo de autorização padrão usado por vários dos sites principais, as credenciais e senhas do usuário não são passadas de um computador a outro. Em vez disso, a autenticação e autorização são baseadas na troca de tokens de segurança; esses tokens concedem acesso a um conjunto específico de recursos por um período determinado.
  
A autenticação com o OAuth geralmente envolve três partes: um servidor de autorização individual e dois realms que precisam se comunicar entre si. (Você também pode fazer a autenticação de servidor-para-servidor sem usar um servidor de autorização, um processo que será discutido posteriormente neste documento.) Tokens de segurança são emitidos pelo servidor de autorização (também conhecido como um security token servidor) para os dois territórios que precisam se comunicar; Verifique se estes tokens, que comunicações provenientes de um território devem ser confiável pelo território outro. Por exemplo, o servidor de autorização pode emitir tokens que verifique se os usuários de um Skype específico para Business Server 2015 realm serão capazes de acessar um realm do Exchange 2013 especificado e vice-versa.
  
> [!NOTE]
> Um realm é simplesmente um contêiner de segurança. Por padrão, o Skype para Business Server 2015 usa o domínio SIP padrão como seu território OAuth. Namespaces SIP adicionais são adicionadas à lista Nome Alternativo da Entidade no certificado OAuth. 
  
Skype para Business Server 2015 oferece suporte a três cenários de autenticação de servidor-para-servidor. Com o Skype para Business Server 2015, você pode:
  
- Configure a autenticação de servidor-para-servidor entre uma instalação local do Skype para Business Server 2015 e uma instalação local do Exchange 2013 e/ou o SharePoint Server.
    
- Configure a autenticação de servidor-para-servidor entre um par de componentes do Office 365 (por exemplo, entre o Microsoft Exchange Server e do Skype para Business Server, ou entre Skype para Business Server 2015 e o SharePoint).
    
- Configure a autenticação de servidor-para-servidor em um ambiente entre locais (isto é, autenticação de servidor-para-servidor entre o servidor de um local e um componente do Office 365).
    
Observe que, neste momento, somente Exchange 2013, SharePoint Server, Lync Server 2013 e Skype para a autenticação de servidor-para-servidor de suporte Business Server 2015. Se você não estiver executando um desses servidores, em seguida, não será capaz de implementar totalmente a autenticação OAuth.
  
Ele também deve ser apontado check-out desse servidor-para-servidor autenticação é opcional: se Skype para Business Server 2015 não precisa se comunicar com outros servidores (por exemplo, o Exchange 2013) e autenticação de servidor-para-servidor pode ser ignorada todo. Se a autenticação de servidor-para-servidor já está configurada para o Lync Server 2013 e outros aplicativos, não é preciso ser novamente fazê-lo para Skype para Business Server 2015. 
  
No entanto, a autenticação de servidor-para-servidor é necessária se você quiser usar alguns dos recursos no Skype para negócios 2015 do servidor, como "repositório unificado de contatos." Com o armazenamento unificado de contatos, Skype Business Server 2015 informações de contato é armazenado no Exchange 2013 em vez de no Skype para Business Server. Isso permite que os usuários tenham um único conjunto de contatos está prontamente acessível no Skype para negócios, Outlook ou Outlook Web Access. Como o armazenamento unificado de contatos requer Skype para 2015 do servidor de negócios compartilhar informações com o Exchange 2013, você deve usar a autenticação de servidor-para-servidor para implantar o recurso. Autenticação de servidor-para-servidor também será obrigatório se você optar por usar o arquivamento do Exchange, no qual as transcrições de sessões de mensagens instantâneas são salvos como emails do Exchange 2013 e não como registros de banco de dados individual.
  
Para a versão do Office 365 do Skype para Business Server para se comunicar com seu equivalente do Exchange, Skype para Business Server 2015 deve obter um token de segurança do servidor de autorização. Skype para Business Server usa esse token de segurança para identificar-se ao Exchange. A versão do Office 365 do Exchange deve passar o mesmo processo para se comunicar com Skype para Business Server 2015.
  
No entanto, para uma autenticação de servidor para servidor ente dois servidores da Microsoft, não é preciso usar um servidor de token terceirizado. Produtos de servidor, como Skype para Business Server 2015 e Exchange 2013 têm um servidor de token interno que pode ser usado para fins de autenticação com outros servidores da Microsoft (por exemplo, o SharePoint Server) que oferecem suporte à autenticação de servidor-para-servidor. Por exemplo, Skype para Business Server 2015 pode emitir assinar um token de segurança por si só e usar esse token para se comunicar com o Exchange 2013. Em um caso como esse, não há a necessidade de um servidor de token terceirizado.
  
Para configurar a autenticação de servidor-para-servidor para uma implementação local do Skype para Business Server 2015, você deve fazer duas coisas:
  
- Atribua um certificado para o Skype interna para o emissor de token Business Server 2015.
    
- Configure o servidor que Skype para Business Server 2015 se comunicar com um "aplicativo de parceiro". Por exemplo, se Skype para Business Server 2015 precisa se comunicar com o Exchange 2013, em seguida, você precisará configurar o Exchange para ser aplicativo parceiro.
    
> [!NOTE]
> Um "aplicativo de parceiro" é qualquer aplicativo Skype para Business Server 2015 pode trocar diretamente tokens de segurança, sem precisar passar por um servidor de token de segurança de terceiros. 
  
Observe que o OAuth é uma parte essencial do produto e não pode ser desabilitado, nem removido.
  
## <a name="see-also"></a>Consulte também

[Atribuir um certificado de autenticação de servidor-para-servidor ao Skype para Business Server 2015](assign-a-server-to-server-certificate.md)
  
[Configurar um ambiente híbrido no Skype para Business Server 2015](configure-a-hybrid-environment.md)