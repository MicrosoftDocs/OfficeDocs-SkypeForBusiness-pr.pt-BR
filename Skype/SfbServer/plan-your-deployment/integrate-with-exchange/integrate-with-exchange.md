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
description: 'Resumo: revise este tópico para obter informações sobre como integrar o Skype for Business Server com Exchange Server 2016 ou Exchange Server 2013.'
ms.openlocfilehash: 6b2fdab1a25db7d56c99e965877cb684d102da36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098667"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plano para integrar o Skype for Business e o Exchange
 
**Resumo:** Revise este tópico para obter informações sobre como integrar o Skype for Business Server com o Exchange Server 2016 ou Exchange Server 2013.
  
Antes de integrar o Skype for Business Server e o Exchange Server, você deve garantir que o Exchange Server e o Skype for Business Server estão totalmente instalados e em execução. 
  
Para obter detalhes sobre como instalar Exchange Server, consulte a documentação Exchange Server Planejamento e Implantação para sua versão do Exchange. 
   
Depois que os servidores estão em execução, você deve atribuir certificados de autenticação de servidor para servidor ao Skype for Business Server e Exchange Server; esses certificados permitem que o Skype for Business Server e Exchange Server trocar informações e se comunicarem entre si. Quando você instala Exchange Server, um certificado auto-assinado com o nome Microsoft Exchange Server Certificado Auth é criado para você. Esse certificado, que pode ser encontrado no armazenamento de certificados do computador local, deve ser usado para autenticação de servidor para servidor em Exchange Server. Para obter detalhes sobre a atribuição de certificados Exchange Server, consulte [Configure Mail Flow and Client Access](/exchange/configure-mail-flow-and-client-access-exchange-2013-help).
  
Para o Skype for Business Server, você pode usar um certificado existente do Skype for Business Server como seu certificado de autenticação de servidor para servidor; por exemplo, seu certificado padrão também pode ser usado como o certificado OAuthTokenIssuer. O Skype for Business Server permite que você use qualquer certificado de servidor Web como o certificado para autenticação de servidor para servidor, desde que:
  
- O certificado inclua o nome de seu domínio SIP no campo de Entidade.
    
- O mesmo certificado esteja configurado como o certificado do OAuthTokenIssuer em todos os seus servidores Front-End.
    
- O certificado tenha no mínimo 2048 bits.
    
Para obter detalhes sobre certificados de autenticação de servidor para servidor para o Skype for Business Server, consulte [Assign a server-to-server authentication certificate to Skype for Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Depois que os certificados foram atribuídos, você deve configurar o serviço de descoberta automática em Exchange Server. Em Exchange Server, o serviço de descoberta automática configura perfis de usuário e fornece acesso aos serviços do Exchange quando os usuários fizerem logoff no sistema. Os usuários apresentam seus endereços de email e senhas ao serviço de descoberta automática; por sua vez, os serviços fornecem aos usuários informações como:
  
- Informações de conexão para conectividade interna e externa com Exchange Server.
    
- O local do servidor de Caixa de Correio do usuário.
    
- URLs para recursos do Outlook como informações de livre/ocupado, Unificação de Mensagens e o catálogo de endereços offline.
    
- Configurações do servidor do Outlook Anywhere.
    
O serviço de descoberta automática deve ser configurado para que você possa integrar o Skype for Business Server e Exchange Server. Você pode verificar se o serviço de descoberta automática foi configurado executando o seguinte comando no Shell de Gerenciamento Exchange Server e verificando o valor da propriedade AutoDiscoverServiceInternalUri:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Se esse valor estiver em branco, você deverá atribuir um URI ao serviço de descoberta automática. Normalmente, esse URI terá uma aparência semelhante a esta: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Você pode atribuir o URI de descoberta automática executando um comando similar a este:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Para obter detalhes sobre o serviço de descoberta automática, consulte [Autodiscover Service](/Exchange/architecture/client-access/autodiscover).
  
Depois que o serviço de descoberta automática tiver sido configurado, você deverá modificar as configurações do OAuth do Skype for Business Server; isso garante que o Skype for Business Server saiba onde encontrar o serviço de descoberta automática. Para modificar as configurações do OAuth no Skype for Business Server, execute o seguinte comando no Shell de Gerenciamento do Skype for Business Server. Ao executar esse comando, especifique o URI para o serviço de descoberta automática em execução em seu Exchange Server e que você use **autodiscover.svc** para apontar para o local do serviço em vez de **autodiscover.xml** (que aponta para o arquivo XML usado pelo serviço):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> O parâmetro Identity no comando anterior é opcional; isso porque o Skype for Business Server só permite que você tenha uma única coleção global de configurações OAuth. Dentre outras coisas, isso significa que você pode configurar a URL de descoberta automática usando este comando um pouco mais simples: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> Caso não esteja familiarizado com a tecnologia, o OAuth é um protocolo de autorização padrão usado por vários websites importantes. Com o OAuth, as credenciais de usuário e senhas não são passadas de um computador a outro. Ao invés disso, a autenticação e autorização são baseadas na troca de tokens de segurança; estas tokens concedem acesso a um conjunto específico de recursos por um período determinado de tempo. 
  
Além de configurar o serviço de descoberta automática, você também deve criar um registro DNS para o serviço que aponta para sua Exchange Server. Por exemplo, se seu serviço de descoberta automática estiver localizado no autodiscover.litwareinc.com, você precisará criar um registro DNS para autodiscover.litwareinc.com que resolva o nome de domínio totalmente qualificado do seu Exchange Server (por exemplo, atl-exchange-001.litwareinc.com).
  
Se você estiver integrando o Skype for Business Server com o Exchange Online, suas [próximas](../../deploy/integrate-with-exchange-server/outlook-web-app.md)etapas estão em Configurar a integração entre o Skype for Business Server local e o Outlook Web App , caso contrário, consulte Integrar o [Skype for Business Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)com Exchange Server .
  
## <a name="feature-support"></a>Suporte a recursos
<a name="feature_support"> </a>

>[!Important]
> O Skype for Business Online será retirado em 31 de julho de 2021 depois que as integrações do Exchange listadas abaixo que incluem o serviço não terão mais suporte.

A tabela a seguir detalha os recursos suportados em várias combinações de online ou local para Exchange e Skype for Business.
  
||**Exchange 2016/2013/2010 (local) + Skype for Business Server (local)**|**Exchange Online + Skype for Business Server (local)**|**Exchange 2010 (local) + Skype for Business Online**|**Exchange 2016/2013(on-premises) + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Presença no Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Responder via IM, Chamada PSTN, Chamada do Skype ou Chamada de Vídeo de um email do Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Agendar e participar de reuniões online por meio do Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Presença no Outlook Web App  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |S  <br/> |
|Responder via IM, Chamada PSTN, Chamada do Skype ou Chamada de Vídeo de um email do OWA  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |S  <br/> |
|Agendar e participar de reuniões online por meio do Outlook Web App  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |S  <br/> |
|IM/Presença em Clientes Móveis  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Participar de reuniões online em clientes Móveis  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Publicar status com base em informações de livre/ocupado do calendário do Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Lista de contatos (por meio do Unified Contact Store)  <br/> |Y (precisa do Exchange 2016/2013)  <br/> |S  <br/> |N  <br/> |N  <br/> |S  <br/> |
|Foto de contato de alta resolução (requer clientes do Lync 2013 ou skype for Business no mínimo. Não há suporte para LWA, aplicativos móveis, Lync 2010, Lync para Mac e outros clientes mais antigos.)  <br/> |Y (precisa do Exchange 2016/2013)  <br/> |S  <br/> |N  <br/> |S  <br/> |S  <br/> |
|Delegação de reunião  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Histórico de Conversas Perdidas e Logs de Chamadas são gravados na caixa de correio do exchange do usuário  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Conteúdo de Arquivamento (IM e Reunião) no Exchange  <br/> |Y (precisa do Exchange 2016/2013)  <br/> |S  <br/> |N  <br/> |N  <br/> |S  <br/> |
|Pesquisar conteúdo arquivado  <br/> |Y (precisa do Exchange 2016/2013)  <br/> |S  <br/> |N  <br/> |N  <br/> |S  <br/> |
|Caixa Postal de UM do Exchange  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Histórico da Conversa do Lado do Servidor  <br/> |S  <br/> |S  <br/> |N  <br/> |S  <br/> |S  <br/> |

> [!NOTE]
> Há um serviço de Caixa Postal na Nuvem com suporte para Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015 e Lync Server 2013.
> 

## <a name="see-also"></a>Confira também
<a name="feature_support"> </a>

[Configurar a integração entre o Skype for Business Server local e o Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurar o OAuth entre o Skype for Business Online e o Exchange no local](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrar o Skype for Business Server com Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Como integrar o Exchange Server 2013 com o Lync Server 2013, o Skype for Business Online ou uma implantação híbrida do Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-hybrid-deployments)
  
[Configurar aplicativos parceiros no Skype for Business Server e Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)