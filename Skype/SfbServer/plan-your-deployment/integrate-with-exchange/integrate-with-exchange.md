---
title: Plano para integrar o Skype for Business e o Exchange
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Resumo: revise este tópico para obter informações sobre como integrar o Skype for Business Server com o Exchange Server 2016 ou Exchange Server 2013.'
ms.openlocfilehash: 81217886028db9e8cb04296e5d665aada3a3337683f4b8276fb13d454cdc4b76
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284641"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plano para integrar o Skype for Business e o Exchange
 
**Resumo:** Revise este tópico para obter informações sobre como integrar Skype for Business Server com Exchange Server 2016 ou Exchange Server 2013.
  
Antes de integrar Skype for Business Server e Exchange Server, certifique-se de que Exchange Server e Skype for Business Server estão totalmente instalados e em execução. 
  
Para obter detalhes sobre como instalar Exchange Server, consulte a documentação Exchange Server Planejamento e Implantação para sua versão de Exchange. 
   
Depois que os servidores estão em execução, você deve atribuir certificados de autenticação de servidor para servidor a Skype for Business Server e Exchange Server; esses certificados permitem Skype for Business Server e Exchange Server trocar informações e se comunicar entre si. Quando você instala Exchange Server, um certificado auto-assinado com o nome Microsoft Exchange Server Certificado Auth é criado para você. Esse certificado, que pode ser encontrado no armazenamento de certificados do computador local, deve ser usado para autenticação de servidor para servidor em Exchange Server. Para obter detalhes sobre a atribuição de certificados Exchange Server, consulte [Configure Mail Flow and Client Access](/exchange/configure-mail-flow-and-client-access-exchange-2013-help).
  
Para Skype for Business Server você pode usar um certificado Skype for Business Server existente como seu certificado de autenticação de servidor para servidor; por exemplo, seu certificado padrão também pode ser usado como o certificado OAuthTokenIssuer. Skype for Business Server permite que você use qualquer certificado de servidor Web como o certificado para autenticação de servidor para servidor, desde que:
  
- O certificado inclua o nome de seu domínio SIP no campo de Entidade.
    
- O mesmo certificado esteja configurado como o certificado do OAuthTokenIssuer em todos os seus servidores Front-End.
    
- O certificado tenha no mínimo 2048 bits.
    
Para obter detalhes sobre certificados de autenticação de servidor para servidor para Skype for Business Server, consulte Atribuir um certificado de autenticação de servidor para servidor a [Skype for Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Depois que os certificados foram atribuídos, você deve configurar o serviço de descoberta automática no Exchange Server. Em Exchange Server, o serviço de descoberta automática configura perfis de usuário e fornece acesso a serviços Exchange quando os usuários fizerem logoff no sistema. Os usuários apresentam seus endereços de email e senhas ao serviço de descoberta automática; por sua vez, os serviços fornecem aos usuários informações como:
  
- Informações de conexão para conectividade interna e externa com Exchange Server.
    
- O local do servidor de Caixa de Correio do usuário.
    
- URLs para recursos do Outlook como informações de livre/ocupado, Unificação de Mensagens e o catálogo de endereços offline.
    
- Configurações do servidor do Outlook Anywhere.
    
O serviço de descoberta automática deve ser configurado para que você possa integrar Skype for Business Server e Exchange Server. Você pode verificar se o serviço de descoberta automática foi configurado executando o seguinte comando no Shell de Gerenciamento do Exchange Server e verificando o valor da propriedade AutoDiscoverServiceInternalUri:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Se esse valor estiver em branco, você deverá atribuir um URI ao serviço de descoberta automática. Normalmente, esse URI terá uma aparência semelhante a esta: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Você pode atribuir o URI de descoberta automática executando um comando similar a este:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Para obter detalhes sobre o serviço de descoberta automática, consulte [Autodiscover Service](/Exchange/architecture/client-access/autodiscover).
  
Depois que o serviço de descoberta automática tiver sido configurado, você deverá modificar as configurações Skype for Business Server OAuth; isso garante que Skype for Business Server saiba onde encontrar o serviço de descoberta automática. Para modificar as configurações do OAuth no Skype for Business Server, execute o seguinte comando no Shell de Gerenciamento Skype for Business Server. Ao executar esse comando, especifique o URI para o serviço de descoberta automática em execução em seu Exchange Server e use **autodiscover.svc** para apontar para o local de serviço em vez de **autodiscover.xml** (que aponta para o arquivo XML usado pelo serviço):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> O parâmetro Identity no comando anterior é opcional; isso porque Skype for Business Server permite que você tenha uma única coleção global de configurações OAuth. Dentre outras coisas, isso significa que você pode configurar a URL de descoberta automática usando este comando um pouco mais simples: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> Caso não esteja familiarizado com a tecnologia, o OAuth é um protocolo de autorização padrão usado por vários websites importantes. Com o OAuth, as credenciais de usuário e senhas não são passadas de um computador a outro. Ao invés disso, a autenticação e autorização são baseadas na troca de tokens de segurança; estas tokens concedem acesso a um conjunto específico de recursos por um período determinado de tempo. 
  
Além de configurar o serviço de descoberta automática, você também deve criar um registro DNS para o serviço que aponta para seu Exchange Server. Por exemplo, se o serviço de descoberta automática estiver localizado no autodiscover.litwareinc.com, você precisará criar um registro DNS para autodiscover.litwareinc.com que resolva o nome de domínio totalmente qualificado do seu Exchange Server (por exemplo, atl-exchange-001.litwareinc.com).
  
Se você estiver integrando o Skype for Business Server com o Exchange Online, suas próximas etapas estão em Configurar a integração entre o Skype for Business Server local e [o Outlook Web App,](../../deploy/integrate-with-exchange-server/outlook-web-app.md)caso contrário, consulte [Integrar](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)Skype for Business Server com Exchange Server .
  
## <a name="feature-support"></a>Suporte a recursos
<a name="feature_support"> </a>

>[!Important]
> Skype for Business Online será retirado em 31 de julho de 2021 depois que as integrações Exchange listadas abaixo que incluem o serviço não serão mais suportadas.

A tabela a seguir detalha os recursos com suporte em várias combinações online ou local para Exchange e Skype for Business.
  
||**Exchange 2016/2013/2010 (local) + Skype for Business Server (local)**|**Exchange Online + Skype for Business Server (local)**|**Exchange 2010 (local) + Skype for Business Online**|**Exchange 2016/2013(local) + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Presença no Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Responder via IM, Chamada PSTN, Skype Chamada ou Vídeo de um email Outlook email  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Agendar e participar de reuniões online por meio Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Presença no Outlook Web App  <br/> |S  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Responder por IM, Chamada PSTN, Skype Chamada ou Chamada de Vídeo de um email do OWA  <br/> |S  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Agendar e participar de reuniões online por meio Outlook Web App  <br/> |S  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|IM/Presença em Clientes Móveis  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Participar de reuniões online em clientes Móveis  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Publicar status com base em Outlook de agenda livre/ocupado  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Lista de contatos (por meio do Unified Contact Store)  <br/> |Y (precisa Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Foto de contato de alta resolução (requer clientes do Lync 2013 ou Skype for Business no mínimo. Não há suporte para LWA, aplicativos móveis, Lync 2010, Lync para Mac e outros clientes mais antigos.)  <br/> |Y (precisa Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |S  <br/> |S  <br/> |
|Delegação de reunião  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Histórico de Conversas Perdidas e Logs de Chamadas são gravados na caixa de correio do exchange do usuário  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Conteúdo de Arquivamento (IM e Reunião) em Exchange  <br/> |Y (precisa Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Pesquisar conteúdo arquivado  <br/> |Y (precisa Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Exchange Caixa Postal de UM  <br/> |S  <br/> |Y  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Histórico da Conversa do Lado do Servidor  <br/> |S  <br/> |Y  <br/> |N  <br/> |S  <br/> |S  <br/> |

> [!NOTE]
> Há um serviço Caixa postal na Nuvem com suporte para o Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015 e Lync Server 2013.
> 

## <a name="see-also"></a>Confira também
<a name="feature_support"> </a>

[Configurar a integração entre o Skype for Business Server local e Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurar o OAuth entre Skype for Business Online e Exchange local](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrar Skype for Business Server com Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Como integrar o Exchange Server 2013 com o Lync Server 2013, Skype for Business Online ou uma implantação híbrida do Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[Configurar aplicativos parceiros em Skype for Business Server e Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)