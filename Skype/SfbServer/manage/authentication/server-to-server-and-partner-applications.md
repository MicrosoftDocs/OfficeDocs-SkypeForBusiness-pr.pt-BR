---
title: Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos parceiros no Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 38848373-c8c6-4097-bf7f-699fe471348d
description: 'Resumo: Gerenciar o OAuth e aplicativos parceiros Skype for Business Server.'
---

# <a name="manage-server-to-server-authentication-oauth-and-partner-applications-in-skype-for-business-server"></a>Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos parceiros no Skype for Business Server
 
**Resumo:** Gerenciar aplicativos OAuth e parceiros em Skype for Business Server.
  
Skype for Business Server ser capaz de se comunicar com segurança e de forma perfeita com outros aplicativos e produtos de servidor. Por exemplo, você pode configurar o Skype for Business Server para que os dados de contato e/ou os dados de arquivamento sejam armazenados no Microsoft Exchange Server 2013; no entanto, isso só poderá ser feito se Skype for Business Server e Exchange  são capazes de se comunicar com segurança entre si. Da mesma forma, você pode agendar uma conferência Skype for Business Server de dentro do Office Web Apps Server; novamente, isso só poderá ser feito se os dois servidores (SharePoint e Skype for Business Server) confiarem um no outro. Embora seja possível usar um mecanismo de autenticação para comunicação entre Skype for Business Server e Exchange, mas um mecanismo separado para Skype for Business Server e SharePoint  comunicação, uma abordagem melhor e mais eficiente é usar um método padronizado para toda a autenticação e autorização de servidor para servidor.
  
Usar um único método padronizado para autenticação de servidor para servidor é a abordagem tomada por Skype for Business Server. Iniciado com Office versão do Office Servers 2013, o Skype for Business Server (bem como outros produtos do Microsoft Server, incluindo o Exchange Server e o SharePoint Server) suportava o protocolo OAuth (Autorização Aberta) para autenticação e autorização de servidor para servidor. Com o OAuth, um protocolo de autorização padrão usado por vários dos sites principais, as credenciais e senhas do usuário não são passadas de um computador a outro. Em vez disso, a autenticação e autorização são baseadas na troca de tokens de segurança; esses tokens concedem acesso a um conjunto específico de recursos por um período determinado.
  
A autenticação com o OAuth geralmente envolve três partes: um servidor de autorização individual e dois realms que precisam se comunicar entre si. (Você também pode fazer autenticação de servidor para servidor sem usar um servidor de autorização, um processo que será discutido posteriormente neste documento.) Tokens de segurança são emitidos pelo servidor de autorização (também conhecido como servidor de token de segurança) para os dois domínios que precisam se comunicar; esses tokens verificam se as comunicações provenientes de um domínio devem ser confiáveis pelo outro realm. Por exemplo, o servidor de autorização pode emitir tokens que verifiquem se os usuários de um domínio Skype for Business Server específicos podem acessar um domínio Exchange especificado e vice-versa.
  
> [!NOTE]
> Um realm é simplesmente um contêiner de segurança. Por padrão, Skype for Business Server usa seu domínio SIP padrão como seu realm OAuth. Namespaces SIP adicionais são adicionados à lista Nome Alternativo de Assunto no certificado OAuth. 
  
Skype for Business Server suporta três cenários de autenticação de servidor para servidor. Com Skype for Business Server, você pode:
  
- Configure a autenticação de servidor para servidor entre uma instalação local do Skype for Business Server e uma instalação local do Exchange e/ou SharePoint Server.
    
- Configurar a autenticação de servidor para servidor entre um par de componentes Microsoft 365 ou Office 365 (por exemplo, entre Microsoft Exchange Server e Skype for Business Server, ou entre Skype for Business Server e SharePoint).
    
- Configure a autenticação de servidor para servidor em um ambiente entre locais (ou seja, autenticação de servidor para servidor entre um servidor local e um componente Microsoft 365 ou Office 365).
    
Observe que, neste momento, somente o Exchange 2013, o SharePoint Server, o Lync Server 2013, o Skype for Business Server 2015 e o Skype for Business 2019 suportam a autenticação de servidor para servidor; se você não estiver executando um desses servidores, não poderá implementar totalmente a autenticação OAuth.
  
Também deve ser apontado que a autenticação de servidor para servidor é opcional: se o Skype for Business Server não precisar se comunicar com outros servidores (como o Exchange), a autenticação de servidor para servidor poderá ser ignorada completamente. Se a autenticação de servidor para servidor já estiver configurada para o Lync Server 2013 e outros aplicativos, não será necessário reajustá-la para Skype for Business Server. 
  
No entanto, a autenticação de servidor para servidor é necessária se você quiser usar alguns dos recursos no Skype for Business Server, como o "armazenamento unificado de contatos". Com o armazenamento unificado de contatos, Skype for Business Server informações de contato são armazenadas no Exchange em vez de no Skype for Business Server; isso permite que os usuários tenham um único conjunto de contatos que é prontamente acessível de Skype for Business, Outlook, ou Outlook Web Access. Como o armazenamento de contatos unificado exige Skype for Business Server para compartilhar informações com Exchange, você deve usar a autenticação de servidor para servidor para implantar o recurso. A autenticação de servidor para servidor também será necessária se você optar por usar Exchange arquivamento, no qual as transcrições de sessões de mensagens instantâneas são salvas como emails Exchange e não como registros de banco de dados individuais.
  
Para que Microsoft 365 ou Office 365 do Skype for Business Server se comuniquem com seu equivalente Exchange, o Skype for Business Server deve primeiro obter um token de segurança do servidor de autorização. Skype for Business Server usa esse token de segurança para se identificar para Exchange. As Microsoft 365 ou Office 365 de Exchange devem passar pelo mesmo processo para se comunicar com Skype for Business Server.
  
No entanto, para uma autenticação de servidor para servidor ente dois servidores da Microsoft, não é preciso usar um servidor de token terceirizado. Os produtos de servidor, como Skype for Business Server e Exchange, têm um servidor de tokens integrado que pode ser usado para fins de autenticação com outros servidores Microsoft (como o SharePoint Server) que suportam a autenticação de servidor para servidor. Por exemplo, Skype for Business Server pode emitir e assinar um token de segurança por si só e, em seguida, usar esse token para se comunicar com Exchange. Em um caso como esse, não há a necessidade de um servidor de token terceirizado.
  
Para configurar a autenticação de servidor para servidor para uma implementação local do Skype for Business Server, você deve fazer duas coisas:
  
- Atribua um certificado ao emissor Skype for Business Server token integrado.
    
- Configure o servidor com o Skype for Business Server se comunicará para ser um "aplicativo parceiro". Por exemplo, se Skype for Business Server precisa se comunicar com Exchange, você precisará configurar o Exchange para ser um aplicativo parceiro.
    
> [!NOTE]
> Um "aplicativo parceiro" é qualquer aplicativo com o Skype for Business Server que possa trocar tokens de segurança diretamente, sem precisar passar por um servidor de tokens de segurança de terceiros. 
  
Observe que o OAuth é uma parte principal do produto e não pode ser desabilitado ou removido.
  
## <a name="see-also"></a>Confira também

[Atribua um certificado de autenticação de servidor para servidor Skype for Business Server](assign-a-server-to-server-certificate.md)
  
[Configurar um ambiente híbrido em Skype for Business Server](configure-a-hybrid-environment.md)
