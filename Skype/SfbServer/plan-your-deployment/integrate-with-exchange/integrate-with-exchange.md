---
title: Plano para integrar o Skype for Business e o Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Resumo: Confira este tópico para obter informações sobre como integrar o Skype for Business Server com o Exchange Server 2016 ou o Exchange Server 2013.'
ms.openlocfilehash: 54a079a550b1c915d9ffc124b1608a3fd3f2a5ef
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991476"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plan to integrate Skype for Business and Exchange
 
**Resumo:** Confira este tópico para obter informações sobre como integrar o Skype for Business Server com o Exchange Server 2016 ou o Exchange Server 2013.
  
Antes de poder integrar o Skype for Business Server e o Exchange Server, você deve garantir que tanto o Exchange Server quanto o Skype for Business Server estejam instalados e em funcionamento completo. 
  
Para obter detalhes sobre como instalar o Exchange Server, consulte a documentação de planejamento e implantação do Exchange Server para a sua versão do Exchange. 
   
Depois que os servidores estiverem em execução, você deverá atribuir certificados de autenticação de servidor a servidor ao Skype for Business Server e ao Exchange Server; esses certificados permitem que o Skype for Business Server e o Exchange Server troquem informações e comuniquem-se uns com os outros. Quando você instala o Exchange Server, um certificado autoassinado com o nome certificado de autenticação do Microsoft Exchange Server é criado para você. Esse certificado, que pode ser encontrado no repositório de certificados do computador local, deve ser usado para autenticação de servidor para servidor no Exchange Server. Para obter detalhes sobre como atribuir certificados no Exchange Server, consulte [Configurar o fluxo de emails e o acesso do cliente](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Para o Skype for Business Server, você pode usar um certificado existente do Skype for Business Server como certificado de autenticação de servidor para servidor; por exemplo, o certificado padrão também pode ser usado como o certificado OAuthTokenIssuer. O Skype for Business Server permite que você use qualquer certificado de servidor Web como o certificado para autenticação de servidor para servidor desde que:
  
- O certificado inclua o nome de seu domínio SIP no campo de Entidade.
    
- O mesmo certificado está configurado como o certificado OAuthTokenIssuer em todos os seus servidores Front-End.
    
- O certificado tenha no mínimo 2048 bits.
    
Para obter detalhes sobre certificados de autenticação de servidor para servidor para o Skype for Business Server, consulte [atribuir um certificado de autenticação de servidor para servidor ao Skype for Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Após a atribuição dos certificados, você deve configurar o serviço de descoberta automática no Exchange Server. No Exchange Server, o serviço de descoberta automática configura perfis de usuário e fornece acesso aos serviços do Exchange quando os usuários fazem logon no sistema. Os usuários apresentam seus endereços de email e senhas ao serviço de descoberta automática; por sua vez, os serviços fornecem aos usuários informações como:
  
- Informações de conexão para conectividade interna e externa ao Exchange Server.
    
- O local do servidor de caixa de correio do usuário.
    
- URLs para recursos do Outlook como informações de livre/ocupado, Unificação de Mensagens e o catálogo de endereços offline.
    
- Configurações do servidor do Outlook Anywhere.
    
O serviço de descoberta automática deve ser configurado para que você possa integrar o Skype for Business Server e o Exchange Server. Você pode verificar se o serviço de descoberta automática foi ou não configurado executando o seguinte comando no Shell de gerenciamento do Exchange Server e verificando o valor da propriedade AutoDiscoverServiceInternalUri:
  
```PowerShell
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Se esse valor estiver em branco, você deverá atribuir um URI para o serviço de descoberta automática. Geralmente, esse URI tem uma aparência semelhante a esta:https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Você pode atribuir o URI de descoberta automática executando um comando similar a este:
  
```PowerShell
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Para obter detalhes sobre o serviço de descoberta automática, consulte [serviço de descoberta automática](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Após a configuração do serviço de descoberta automática, você deve modificar as configurações de configuração OAuth do Skype for Business Server; Isso garante que o Skype for Business Server saiba onde encontrar o serviço de descoberta automática. Para modificar as configurações de configuração OAuth no Skype for Business Server, execute o seguinte comando no Shell de gerenciamento do Skype for Business Server. Ao executar esse comando, certifique-se de especificar o URI para o serviço de descoberta automática em execução no seu servidor do Exchange e se você usa o **autodiscover. svc** para apontar para o local do serviço em vez do **autodiscover. xml** (que aponta para o arquivo XML usado pelo serviço):
  
```PowerShell
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> O parâmetro Identity no comando anterior é opcional; Isso porque o Skype for Business Server só permite que você tenha uma única coleção global de configurações de configuração OAuth. Dentre outras coisas, isso significa que você pode configurar a URL de descoberta automática usando este comando um pouco mais simples: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "<https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc>" 
> 
> [!NOTE]
> Caso não esteja familiarizado com a tecnologia, o OAuth é um protocolo de autorização padrão usado por vários websites importantes. Com o OAuth, as credenciais de usuário e senhas não são passadas de um computador a outro. Ao invés disso, a autenticação e autorização são baseadas na troca de tokens de segurança; estas tokens concedem acesso a um conjunto específico de recursos por um período determinado de tempo. 
  
Além de configurar o serviço de descoberta automática, você também deve criar um registro DNS para o serviço que aponta para o servidor Exchange. Por exemplo, se o serviço descoberta automática estiver localizado em autodiscover.litwareinc.com, você precisará criar um registro DNS para o autodiscover.litwareinc.com que é resolvido para o nome de domínio totalmente qualificado do servidor Exchange (por exemplo, atl-exchange-001.litwareinc.com).
  
Se você estiver integrando o Skype for Business Server com o Exchange Online, suas próximas etapas estão em [Configurar a integração entre o Skype for Business Server local e o Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md), caso contrário, consulte [integrar o Skype for Business Server com o Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Suporte aos recursos
<a name="feature_support"> </a>

A tabela a seguir detalha os recursos com suporte em várias combinações de online ou no local para o Exchange e o Skype for Business.
  
||**Exchange 2016/2013/2010 (local) + Skype for Business Server (no local)**|**Exchange Online + Skype for Business Server (no local)**|**Exchange 2010 (local) + Skype for Business Online**|**Exchange 2016/2013 (local) + Skype for Business Online**|**Exchange Online + Skype for Business Online**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Presença no Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Responder via IM, Chamada PSTN, Chamada do Skype ou Chamada de Vídeo a partir de um email do Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Agende e participe de reuniões online via Outlook  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Presença no Outlook Web App  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Responder via IM, Chamada PSTN, Chamada do Skype ou Chamada de Vídeo a partir de um OWA email  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Agende e participe de reuniões online via Outlook Web App  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|IM/Presença em clientes de dispositivos móveis  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Participe de reuniões online em clientes de dispositivos móveis  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Publique o status com base nas informações de ocupado/livre do calendário do Outlook  <br/> |Y  <br/> |S  <br/> |S  <br/> |S  <br/> |Y  <br/> |
|Lista de contatos (via repositório de contato unificado)  <br/> |Sim (requer o Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Foto de contato de alta resolução (requer o Lync 2013 ou clientes do Skype for Business no mínimo. Não há suporte para LWA, aplicativos móveis, Lync 2010, Lync para Mac e outros clientes mais antigos).  <br/> |Sim (requer o Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |S  <br/> |S  <br/> |
|Delegação da reunião  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Histórico de conversas perdidas e logs de chamadas são gravados na caixa de correio do Exchange do usuário  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Arquivamento de conteúdo (IM e reunião) no Exchange  <br/> |Sim (requer o Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Pesquise o conteúdo arquivado  <br/> |Sim (requer o Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Caixa Postal UM do Exchange  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Histórico da Conversa no Lado do Servidor  <br/> |Y  <br/> |S  <br/> |N  <br/> |S  <br/> |S  <br/> |

> [!NOTE]
> Há um serviço de correio de voz na nuvem que é compatível com o Skype for Business Online, o Skype for Business Server 2019, o Skype for Business Server 2015 e o Lync Server 2013.
> 

## <a name="see-also"></a>Confira também
<a name="feature_support"> </a>

[Configurar a integração entre o Skype for Business Server local e o Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurar OAuth entre o Skype for Business Online e o Exchange no local](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrar o Skype for Business Server com o Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Como integrar o Exchange Server 2013 com o Lync Server 2013, o Skype for Business online ou um Lync Server 2013 implantação híbrida](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Configurar aplicativos de parceiros no Skype for Business Server e no Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
