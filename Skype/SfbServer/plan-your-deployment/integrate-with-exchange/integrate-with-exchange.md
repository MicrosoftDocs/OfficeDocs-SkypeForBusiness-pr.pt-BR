---
title: Plano para integrar o Skype for Business e o Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Resumo: Leia este tópico para obter informações sobre como integrar o Skype for Business Server com o Exchange Server 2016 ou o Exchange Server 2013.'
ms.openlocfilehash: d5d2a50e3b3b376bc27a407313944a31dc1352f6
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359257"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plano para integrar o Skype for Business e o Exchange
 
**Resumo:** Leia este tópico para obter informações sobre como integrar o Skype for Business Server com o Exchange Server 2016 ou o Exchange Server 2013.
  
Para que você possa integrar o Skype for Business Server e o Exchange Server, verifique se o Exchange Server e o Skype for Business Server estão totalmente instalados e em execução. 
  
Para obter detalhes sobre como instalar o Exchange Server, consulte a documentação de planejamento e implantação do Exchange Server para sua versão do Exchange. 
   
Depois que os servidores estiverem em execução, você deverá atribuir certificados de autenticação de servidor para servidor ao Skype for Business Server e ao Exchange Server; esses certificados permitem que o Skype for Business Server e o Exchange Server troquem informações e se comuniquem entre si. Quando você instala o Exchange Server, um certificado autoassinado com o nome certificado de autenticação do servidor do Microsoft Exchange é criado para você. Esse certificado, que pode ser encontrado no repositório de certificados do computador local, deve ser usado para a autenticação de servidor para servidor no Exchange Server. Para obter detalhes sobre como atribuir certificados no Exchange Server, consulte [Configurar o fluxo de mensagens e o acesso para cliente](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Para o Skype for Business Server, você pode usar um certificado existente do Skype for Business Server como seu certificado de autenticação de servidor para servidor; por exemplo, seu certificado padrão também pode ser usado como o certificado OAuthTokenIssuer. O Skype for Business Server permite que você use qualquer certificado de servidor Web como o certificado de autenticação de servidor para servidor fornecido por:
  
- O certificado inclua o nome de seu domínio SIP no campo de Entidade.
    
- O mesmo certificado esteja configurado como o certificado do OAuthTokenIssuer em todos os seus servidores Front-End.
    
- O certificado tenha no mínimo 2048 bits.
    
Para obter detalhes sobre certificados de autenticação de servidor para servidor para o Skype for Business Server, consulte [atribuir um certificado de autenticação de servidor para servidor ao Skype for Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Depois que os certificados tiverem sido atribuídos, você deve configurar o serviço de descoberta automática no Exchange Server. No Exchange Server, o serviço de descoberta automática configura perfis de usuário e fornece acesso aos serviços do Exchange quando os usuários fazem logon no sistema. Os usuários apresentam seus endereços de email e senhas ao serviço de descoberta automática; por sua vez, os serviços fornecem aos usuários informações como:
  
- Informações de conexão para conectividade interna e externa para o Exchange Server.
    
- O local do servidor de caixa de correio do usuário.
    
- URLs para recursos do Outlook como informações de livre/ocupado, Unificação de Mensagens e o catálogo de endereços offline.
    
- Configurações do servidor do Outlook Anywhere.
    
O serviço de descoberta automática deve ser configurado para que você possa integrar o Skype for Business Server e o Exchange Server. Você pode verificar se o serviço de descoberta automática foi ou não configurado executando o seguinte comando no Shell de gerenciamento do Exchange Server e verificando o valor da propriedade AutoDiscoverServiceInternalUri:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Se esse valor estiver em branco, você deve atribuir um URI para o serviço de descoberta automática. Normalmente, esse URI terá uma aparência semelhante a esta: https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Você pode atribuir o URI de descoberta automática executando um comando similar a este:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Para obter detalhes sobre o serviço de descoberta automática, consulte [serviço de descoberta automática](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Depois que o serviço de descoberta automática tiver sido configurado, você deverá modificar as definições de configuração de OAuth do Skype for Business Server; Isso garante que o Skype for Business Server saiba onde encontrar o serviço de descoberta automática. Para modificar as definições de configuração do OAuth no Skype for Business Server, execute o seguinte comando no Shell de gerenciamento do Skype for Business Server. Ao executar esse comando, verifique se você especificou o URI para o serviço de descoberta automática em execução no seu servidor do Exchange e se você usa o **autodiscover. svc** para apontar para o local do serviço em vez de **autodiscover.xml** (que aponta para o arquivo XML usado pelo serviço):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> O parâmetro Identity no comando anterior é opcional; Isso ocorre porque o Skype for Business Server permite que você tenha apenas uma única coleção global de definições de configuração OAuth. Dentre outras coisas, isso significa que você pode configurar a URL de descoberta automática usando este comando um pouco mais simples: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl " <https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc> " 
> 
> [!NOTE]
> Caso não esteja familiarizado com a tecnologia, o OAuth é um protocolo de autorização padrão usado por vários websites importantes. Com o OAuth, as credenciais de usuário e senhas não são passadas de um computador a outro. Ao invés disso, a autenticação e autorização são baseadas na troca de tokens de segurança; estas tokens concedem acesso a um conjunto específico de recursos por um período determinado de tempo. 
  
Além de configurar o serviço de descoberta automática, você também deve criar um registro DNS para o serviço que aponta para o seu servidor Exchange. Por exemplo, se o serviço de descoberta automática estiver localizado em autodiscover.litwareinc.com, você precisará criar um registro DNS para autodiscover.litwareinc.com que resolva o nome de domínio totalmente qualificado do seu servidor do Exchange (por exemplo, atl-exchange-001.litwareinc.com).
  
Se você estiver integrando o Skype for Business Server com o Exchange Online, suas próximas etapas estão em [Configurar a integração entre o Skype for Business Server local e o Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), caso contrário, consulte [integrar o Skype for Business Server com o Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Suporte de recurso
<a name="feature_support"> </a>

>[!Important]
> O Skype for Business online será desativado no dia 31 de julho de 2021 depois que as integrações do Exchange listadas abaixo que incluem o serviço não serão mais suportadas.

A tabela a seguir detalha os recursos suportados em várias combinações de online ou local para o Exchange e Skype for Business.
  
||**Exchange 2016/2013/2010 (local) + Skype for Business Server (local)**|**Exchange Online + Skype for Business Server (local)**|**Exchange 2010 (local) + Skype for Business Online**|**Exchange 2016/2013 (local) + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Presença no Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Responder via IM, chamada PSTN, chamada do Skype ou chamada de vídeo de um email do Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Agendar e ingressar em reuniões online por meio do Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Presença no Outlook Web App  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |S  <br/> |
|Responder via IM, chamada PSTN, chamada do Skype ou chamada de vídeo de um email do OWA  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |S  <br/> |
|Agendar e ingressar em reuniões online por meio do Outlook Web App  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |S  <br/> |
|IM/presença em clientes móveis  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Ingressar em reuniões online em clientes móveis  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Publicar status com base nas informações de disponibilidade do calendário do Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Lista de contatos (via repositório unificado de contatos)  <br/> |Y (precisa do Exchange 2016/2013)  <br/> |S  <br/> |N  <br/> |N  <br/> |S  <br/> |
|Foto de contato de alta resolução (requer o Lync 2013 ou o Skype for Business clientes no mínimo. Sem suporte para LWA, aplicativos móveis, Lync 2010, Lync para Mac e outros clientes mais antigos.)  <br/> |Y (precisa do Exchange 2016/2013)  <br/> |S  <br/> |N  <br/> |S  <br/> |S  <br/> |
|Delegação de reunião  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|O histórico de conversas perdidas e os logs de chamadas são gravados na caixa de correio do Exchange do usuário  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Arquivamento de conteúdo (IM e reunião) no Exchange  <br/> |Y (precisa do Exchange 2016/2013)  <br/> |S  <br/> |N  <br/> |N  <br/> |S  <br/> |
|Pesquisar conteúdo arquivado  <br/> |Y (precisa do Exchange 2016/2013)  <br/> |S  <br/> |N  <br/> |N  <br/> |S  <br/> |
|Caixa postal do UM do Exchange  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Histórico de conversa no servidor  <br/> |S  <br/> |S  <br/> |N  <br/> |S  <br/> |S  <br/> |

> [!NOTE]
> Há um serviço de caixa postal em nuvem com suporte para o Skype for Business Online, Skype for Business Server 2019, Skype for Business Server 2015 e Lync Server 2013.
> 

## <a name="see-also"></a>Confira também
<a name="feature_support"> </a>

[Configurar a integração entre o Skype for Business Server local e o Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurar o OAuth entre o Skype for Business Online e o Exchange no local](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrar o Skype for Business Server com o Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Como integrar o Exchange Server 2013 com o Lync Server 2013, o Skype for Business online ou uma implantação híbrida do Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Configurar aplicativos parceiros no Skype for Business Server e no Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
