---
title: Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Resumo: Gerencie o OAuth e os aplicativos parceiros no Skype for Business Server.'
ms.openlocfilehash: ff926440d1f00601eacfb77aadb858063b3e48b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828292"
---
# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Skype for Business Server
 
**Resumo:** Gerenciar aplicativos OAuth e parceiros no Skype for Business Server.
  
O Skype for Business Server deve ser capaz de se comunicar com segurança e sem problemas com outros aplicativos e produtos de servidor. Por exemplo, você pode configurar o Skype for Business Server para que os dados de contato e/ou os dados de arquivamento são armazenados no Microsoft Exchange Server 2013; No entanto, isso só poderá ser feito se o Skype for Business Server e o Exchange puderem se comunicar com segurança entre si. Da mesma forma, você pode agendar uma conferência do Skype for Business Server no Servidor do Office Web Apps; novamente, isso só poderá ser feito se os dois servidores (SharePoint e Skype for Business Server) confiarem um no outro. Embora seja possível usar um mecanismo de autenticação para comunicação entre o Skype for Business Server e o Exchange, mas um mecanismo separado para a comunicação do Skype for Business Server e do SharePoint, uma abordagem melhor e mais eficiente é usar um método padronizado para toda a autenticação e autorização de servidor para servidor.
  
Usar um método único e padronizado para autenticação de servidor para servidor é a abordagem tomada pelo Skype for Business Server. Iniciado com a versão Office Servers 2013, o Skype for Business Server (bem como outros produtos do Microsoft Server, incluindo o Exchange Server e o SharePoint Server) suportava o protocolo OAuth (Open Authorization) para autenticação e autorização de servidor para servidor. Com o OAuth, um protocolo de autorização padrão usado por vários dos sites principais, as credenciais e senhas do usuário não são passadas de um computador a outro. Em vez disso, a autenticação e autorização são baseadas na troca de tokens de segurança; esses tokens concedem acesso a um conjunto específico de recursos por um período determinado.
  
A autenticação com o OAuth geralmente envolve três partes: um servidor de autorização individual e dois realms que precisam se comunicar entre si. (Você também pode fazer a autenticação de servidor para servidor sem usar um servidor de autorização, um processo que será discutido posteriormente neste documento.) Os tokens de segurança são emitidos pelo servidor de autorização (também conhecido como servidor de token de segurança) para os dois realms que precisam se comunicar; esses tokens verificam se as comunicações provenientes de um realm devem ser confiáveis para o outro realm. Por exemplo, o servidor de autorização pode emitir tokens que verificam se os usuários de um realm específico do Skype for Business Server podem acessar um realm especificado do Exchange e vice-versa.
  
> [!NOTE]
> Um realm é simplesmente um contêiner de segurança. Por padrão, o Skype for Business Server usa seu domínio SIP padrão como seu realm OAuth. Namespaces SIP adicionais são adicionados à lista nome alternativo da assunto no certificado OAuth. 
  
O Skype for Business Server oferece suporte a três cenários de autenticação de servidor para servidor. Com o Skype for Business Server, você pode:
  
- Configure a autenticação de servidor para servidor entre uma instalação local do Skype for Business Server e uma instalação local do Exchange e/ou SharePoint Server.
    
- Configure a autenticação de servidor para servidor entre um par de componentes do Microsoft 365 ou Office 365 (por exemplo, entre o Microsoft Exchange Server e o Skype for Business Server ou entre o Skype for Business Server e o SharePoint).
    
- Configure a autenticação servidor para servidor em um ambiente entre locais (ou seja, autenticação de servidor para servidor entre um servidor local e um componente do Microsoft 365 ou Office 365).
    
Observe que, neste momento, apenas o Exchange 2013, o SharePoint Server, o Lync Server 2013, o Skype for Business Server 2015 e o Skype for Business 2019 suportam autenticação de servidor para servidor; se você não estiver executando um desses servidores, não poderá implementar totalmente a autenticação OAuth.
  
Também deve-se apontar que a autenticação de servidor para servidor é opcional: se o Skype for Business Server não precisar se comunicar com outros servidores (como o Exchange), a autenticação de servidor para servidor poderá ser ignorada completamente. Se a autenticação de servidor para servidor já estiver configurada para o Lync Server 2013 e outros aplicativos, não será necessário reempresá-la para o Skype for Business Server. 
  
No entanto, a autenticação de servidor para servidor será necessária se você quiser usar alguns dos recursos no Skype for Business Server, como o "armazenamento unificado de contatos". Com o armazenamento unificado de contatos, as informações de contato do Skype for Business Server são armazenadas no Exchange em vez de no Skype for Business Server; Isso permite que os usuários tenham um único conjunto de contatos prontamente acessíveis no Skype for Business, Outlook ou Outlook Web Access. Como o armazenamento unificado de contatos exige que o Skype for Business Server compartilhe informações com o Exchange, você deve usar a autenticação de servidor para servidor para implantar o recurso. A autenticação de servidor para servidor também é necessária se você optar por usar o arquivamento do Exchange, no qual as transcrições das sessões de mensagens instantâneas são salvas como emails do Exchange, e não como registros de banco de dados individuais.
  
Para que a versão do Skype for Business Server do Microsoft 365 ou Office 365 se comunique com seu equivalente do Exchange, o Skype for Business Server deve primeiro obter um token de segurança do servidor de autorização. Em seguida, o Skype for Business Server usa esse token de segurança para se identificar com o Exchange. As versões do Microsoft 365 ou Office 365 do Exchange devem passar pelo mesmo processo para se comunicar com o Skype for Business Server.
  
No entanto, para uma autenticação de servidor para servidor ente dois servidores da Microsoft, não é preciso usar um servidor de token terceirizado. Produtos de servidor como o Skype for Business Server e o Exchange têm um servidor de token integrado que pode ser usado para fins de autenticação com outros servidores da Microsoft (como o SharePoint Server) que suportam a autenticação de servidor para servidor. Por exemplo, o Skype for Business Server pode emitir e assinar um token de segurança sozinho e, em seguida, usar esse token para se comunicar com o Exchange. Em um caso como esse, não há a necessidade de um servidor de token terceirizado.
  
Para configurar a autenticação de servidor para servidor para uma implementação local do Skype for Business Server, você deve fazer duas coisas:
  
- Atribua um certificado ao emissor de token integrado do Skype for Business Server.
    
- Configure o servidor com o quais o Skype for Business Server se comunicará para ser um "aplicativo parceiro". Por exemplo, se o Skype for Business Server precisar se comunicar com o Exchange, você precisará configurar o Exchange para ser um aplicativo parceiro.
    
> [!NOTE]
> Um "aplicativo parceiro" é qualquer aplicativo que o Skype for Business Server pode trocar diretamente tokens de segurança, sem precisar passar por um servidor de token de segurança de terceiros. 
  
Observe que o OAuth é uma parte fundamental do produto e não pode ser desabilitado ou removido.
  
## <a name="see-also"></a>Confira também

[Atribuir um certificado de autenticação de servidor para servidor ao Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[Configurar um ambiente híbrido no Skype for Business Server](configure-a-hybrid-environment.md)
