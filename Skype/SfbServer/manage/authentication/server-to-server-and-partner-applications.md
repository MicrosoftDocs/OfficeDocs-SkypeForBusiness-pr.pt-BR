---
title: Gerenciar a autenticação de servidor-para-servidor (OAuth) e aplicativos de parceiros no Skype para Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Resumo: Gerencie aplicativos de OAuth e parceiros em Skype para Business Server.'
ms.openlocfilehash: 80ce003d02dff9d88125699117d4de469ed53901
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20994668"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Gerenciar a autenticação de servidor-para-servidor (OAuth) e aplicativos de parceiros no Skype para Business Server
 
**Resumo:** Gerencie aplicativos de OAuth e parceiros em Skype para Business Server.
  
Skype para Business Server deve ser capaz de forma segura e perfeitamente, se comunicar com outros aplicativos e produtos de servidor. Por exemplo, você pode configurar Skype para Business Server para que entre em contato com dados e/ou dados de arquivamento é armazenado no Microsoft Exchange Server 2013; No entanto, isso só pode ser feito se Skype para Business Server e do Exchange é capaz de se comunicar umas com as outras de segurança. Da mesma forma, você pode agendar uma Skype para conferência de Business Server de dentro do Office Web Apps Server; novamente, isso só pode ser feito se os dois servidores (SharePoint e Skype para Business Server) confiem uns nos outros. Embora seja possível usar um mecanismo de autenticação para comunicação entre o Skype para Business Server e do Exchange, mas um mecanismo separado para Skype para comunicação Business Server e do SharePoint, uma abordagem melhor e mais eficiente é usar um método padronizado para todos os servidor-para-servidor autenticação e autorização.
  
Usando uma única, o método padronizado para autenticação de servidor-para-servidor é a abordagem tomada pelo Skype para Business Server. A partir do 2013 release, Skype para Business Server (assim como outros produtos Microsoft Server, incluindo o Exchange 2013 e SharePoint Server) oferece suporte o protocolo OAuth (Open Authorization) para autorização e autenticação de servidor-para-servidor. Com o OAuth, um protocolo de autorização padrão usado por vários dos sites principais, as credenciais e senhas do usuário não são passadas de um computador a outro. Em vez disso, a autenticação e autorização são baseadas na troca de tokens de segurança; esses tokens concedem acesso a um conjunto específico de recursos por um período determinado.
  
A autenticação com o OAuth geralmente envolve três partes: um servidor de autorização individual e dois realms que precisam se comunicar entre si. (Você também pode fazer a autenticação de servidor-para-servidor sem usar um servidor de autorização, um processo que será discutido posteriormente neste documento.) Tokens de segurança são emitidos pelo servidor de autorização (também conhecido como um security token servidor) para os dois territórios que precisam se comunicar; Verifique se estes tokens, que comunicações provenientes de um território devem ser confiável pelo território outro. Por exemplo, o servidor de autorização pode emitir tokens que verifique se os usuários de um Skype específico para o realm Business Server serão capazes de acessar um realm Exchange especificado e vice-versa.
  
> [!NOTE]
> Um realm é simplesmente um contêiner de segurança. Por padrão, o Skype para Business Server usa o domínio SIP padrão como seu território OAuth. Namespaces SIP adicionais são adicionadas à lista Nome Alternativo da Entidade no certificado OAuth. 
  
Skype para Business Server oferece suporte a três cenários de autenticação de servidor-para-servidor. Com o Skype para Business Server, você pode:
  
- Configure a autenticação de servidor-para-servidor entre uma instalação local do Skype para Business Server e uma instalação local do Exchange e/ou o SharePoint Server.
    
- Configure a autenticação de servidor-para-servidor entre um par de componentes do Office 365 (por exemplo, entre o Microsoft Exchange Server e do Skype para Business Server, ou entre Skype para Business Server e o SharePoint).
    
- Configure a autenticação de servidor-para-servidor em um ambiente entre locais (isto é, autenticação de servidor-para-servidor entre o servidor de um local e um componente do Office 365).
    
Observe que, neste momento, só Exchange 2013, SharePoint Server, Lync Server 2013, Skype para Business Server 2015 e Skype para negócios 2019 oferecem suporte à autenticação de servidor-para-servidor; Se você não estiver executando um desses servidores, não será capaz de implementar totalmente a autenticação OAuth.
  
Ele também deve ser apontado check-out desse servidor-para-servidor autenticação é opcional: se Skype para Business Server não precisam se comunicar com outros servidores (por exemplo, Exchange) e autenticação de servidor-para-servidor pode ser ignorada todo. Se a autenticação de servidor-para-servidor já está configurada para o Lync Server 2013 e outros aplicativos, não é preciso ser novamente fazê-lo para Skype para Business Server. 
  
No entanto, a autenticação de servidor-para-servidor é necessária se você quiser usar alguns dos recursos no Skype para Business Server, como "repositório unificado de contatos." Com o armazenamento unificado de contatos, Skype para obter informações de contato do Business Server é armazenada no Exchange, em vez de no Skype por Business Server. Isso permite que os usuários tenham um único conjunto de contatos está prontamente acessível no Skype para negócios, Outlook ou Outlook Web Access. Como o armazenamento unificado de contatos requer Skype para servidor de negócios compartilhar informações com o Exchange, você deve usar a autenticação de servidor-para-servidor para implantar o recurso. Autenticação de servidor-para-servidor também será obrigatório se você optar por usar o arquivamento do Exchange, no qual as transcrições de sessões de mensagens instantâneas são salvos como emails do Exchange e não como registros de banco de dados individual.
  
Para a versão do Office 365 do Skype para Business Server para se comunicar com seu equivalente do Exchange, Skype para Business Server deve obter um token de segurança do servidor de autorização. Skype para Business Server usa esse token de segurança para identificar-se ao Exchange. A versão do Office 365 do Exchange deve passar o mesmo processo para se comunicar com Skype para Business Server.
  
No entanto, para uma autenticação de servidor para servidor ente dois servidores da Microsoft, não é preciso usar um servidor de token terceirizado. Produtos de servidor, como Skype para Business Server e do Exchange tem um servidor de token interno que pode ser usado para fins de autenticação com outros servidores da Microsoft (por exemplo, o SharePoint Server) que oferecem suporte à autenticação de servidor-para-servidor. Por exemplo, Skype para Business Server pode emitir assinar um token de segurança por si só e usar esse token para se comunicar com o Exchange. Em um caso como esse, não há a necessidade de um servidor de token terceirizado.
  
Para configurar a autenticação de servidor-para-servidor para uma implementação local do Skype para Business Server, você deve fazer duas coisas:
  
- Atribua um certificado para o Skype interna para o emissor de token Business Server.
    
- Configure o servidor que irá se comunicar com Skype para Business Server seja um "aplicativo de parceiro". Por exemplo, se Skype para Business Server precisa se comunicar com o Exchange, você precisará configurar o Exchange para ser aplicativo parceiro.
    
> [!NOTE]
> Um "aplicativo de parceiro" é qualquer aplicativo Skype para Business Server pode trocar diretamente tokens de segurança, sem precisar passar por um servidor de token de segurança de terceiros. 
  
Observe que o OAuth é uma parte essencial do produto e não pode ser desabilitado, nem removido.
  
## <a name="see-also"></a>Consulte também

[Atribuir um certificado de autenticação de servidor-para-servidor ao Skype para Business Server](assign-a-server-to-server-certificate.md)
  
[Configurar um ambiente híbrido no Skype para Business Server](configure-a-hybrid-environment.md)