---
title: Plano para integrar o Skype for Business e o Exchange
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ea22beb9-c02e-47cb-836d-97a556969052
description: 'Resumo: Revise neste tópico para obter informações sobre como integrar o Skype para Business Server com o Exchange Server 2016 ou Exchange Server 2013.'
ms.openlocfilehash: 3e94e1ab399e8a8a825826e37a281b377a31037e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892333"
---
# <a name="plan-to-integrate-skype-for-business-and-exchange"></a>Plan to integrate Skype for Business and Exchange
 
**Resumo:** Analise este tópico para obter informações sobre como integrar o Skype para Business Server com o Exchange Server 2016 ou Exchange Server 2013.
  
Antes de você poderá integrar o Skype para Business Server e o Exchange Server, você deve assegurar que o Exchange Server e Skype para Business Server estejam totalmente instalada e para cima e em execução. 
  
Para obter detalhes sobre como instalar o Exchange Server, consulte a documentação de implantação e planejamento do Exchange Server para a sua versão do Exchange. 
   
Depois que os servidores estão em execução, você deve atribuir certificados de autenticação de servidor-para-servidor para ambos os Skype para Business Server e o Exchange Server; Esses certificados permitem Skype para Business Server e o Exchange Server para trocar informações e para se comunicar umas com as outras. Quando você instala o Exchange Server, um certificado autoassinado com o nome do certificado de autenticação do Microsoft Exchange Server é criado para você. Esse certificado, que pode ser encontrado no repositório de certificados do computador local, deve ser usado para autenticação de servidor-para-servidor no servidor Exchange. Para obter detalhes sobre como atribuir certificados no Exchange Server, consulte [Configurar o fluxo de correio e acesso para cliente](https://go.microsoft.com/fwlink/p/?LinkId=268540).
  
Para Skype para Business Server você pode usar um Skype existente para o certificado de servidor de negócios como seu certificado de autenticação de servidor-para-servidor; Por exemplo, o certificado padrão também pode ser usado como o certificado OAuthTokenIssuer. Skype para Business Server permite que você use qualquer certificado de servidor Web, como o certificado para autenticação de servidor-para-servidor desde que:
  
- O certificado inclua o nome de seu domínio SIP no campo de Entidade.
    
- O mesmo certificado está configurado como o certificado OAuthTokenIssuer em todos os seus servidores Front-End.
    
- O certificado tenha no mínimo 2048 bits.
    
Para obter detalhes sobre os certificados de autenticação de servidor-para-servidor do Skype para Business Server, consulte [atribuir um certificado de autenticação de servidor-para-servidor para Skype para Business Server](../../manage/authentication/assign-a-server-to-server-certificate.md).
  
Depois que os certificados foram atribuídos, em seguida, configure o serviço Descoberta automática no servidor Exchange. No Exchange Server, o serviço Descoberta automática configura os perfis de usuário e fornece acesso aos serviços do Exchange quando eles fazem logon no sistema. Os usuários apresentam seus endereços de email e senhas ao serviço de descoberta automática; por sua vez, os serviços fornecem aos usuários informações como:
  
- Informações de Conexão para conectividade interna e externa para o Exchange Server.
    
- O local do servidor de caixa de correio do usuário.
    
- URLs para recursos do Outlook como informações de livre/ocupado, Unificação de Mensagens e o catálogo de endereços offline.
    
- Configurações do servidor do Outlook Anywhere.
    
O serviço Descoberta automática deve ser configurado antes de você poderá integrar o Skype para Business Server e o Exchange Server. Você pode verificar se ou não foi configurado o serviço Descoberta automática executando o seguinte comando do Shell de gerenciamento do Exchange Server e verificando o valor da propriedade AutoDiscoverServiceInternalUri:
  
```
Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List
```

Se este valor estiver em branco, você deve atribuir um URI para o serviço Descoberta automática. Geralmente esse URI terá uma aparência semelhante a esta:https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml
  
Você pode atribuir o URI de descoberta automática executando um comando similar a este:
  
```
Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"
```

Para obter detalhes sobre o serviço de descoberta automática, consulte [Serviço de descoberta automática](https://go.microsoft.com/fwlink/p/?LinkId=268542).
  
Após ter sido configurado o serviço Descoberta automática, você deve modificar o Skype para definições de configuração de negócios servidor OAuth; Isso garante que o Skype para Business Server Saiba onde encontrar o serviço Descoberta automática. Para modificar as definições de configuração OAuth no Skype para Business Server, execute o seguinte comando dentro do Skype do Shell de gerenciamento do servidor de negócios. Ao executar esse comando, não se esqueça de que você especifique o URI para o serviço de descoberta automática executando em seu Exchange Server e que você use **autodiscover.svc** para apontar para o local do serviço em vez de **Autodiscover** (que aponta para o arquivo XML usado pelo serviço):
  
```
Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc" 
```

> [!NOTE]
> O parâmetro Identity no comando anterior é opcional. Isso acontece porque o Skype para Business Server só permite que você tenha uma única coleção global de definições de configuração OAuth. Dentre outras coisas, isso significa que você pode configurar a URL de descoberta automática usando este comando um pouco mais simples: 
> 
> [!NOTE]
> Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "<https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc>" 
> 
> [!NOTE]
> Caso não esteja familiarizado com a tecnologia, o OAuth é um protocolo de autorização padrão usado por vários websites importantes. Com o OAuth, as credenciais de usuário e senhas não são passadas de um computador a outro. Ao invés disso, a autenticação e autorização são baseadas na troca de tokens de segurança; estas tokens concedem acesso a um conjunto específico de recursos por um período determinado de tempo. 
  
Além de configurar o serviço de descoberta automática, você também deve criar um registro DNS para o serviço que aponta para o seu servidor do Exchange. Por exemplo, se o serviço de descoberta automática estiver localizado em autodiscover.litwareinc.com você precisará criar um registro DNS para que se resolva como o nome de domínio totalmente qualificado do seu servidor do Exchange (por exemplo, autodiscover.litwareinc.com ATL-exchange-001).
  
Se você estiver integrando Skype para Business Server com o Exchange Online, sua próxima etapa será [Configurar](../../deploy/integrate-with-exchange-server/outlook-web-app.md)integração entre locais Skype para Business Server e o Outlook Web App, caso contrário, consulte [Skype integra-se para o Business Server com o Exchange Servidor](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
## <a name="feature-support"></a>Suporte aos recursos
<a name="feature_support"> </a>

A tabela a seguir fornece detalhes sobre os recursos suportados em várias combinações de online ou no local do Exchange e do Skype para negócios.
  
||**2013/Exchange 2016/2010 (no local) + Skype para Business Server (no local)**|**O Exchange Online + Skype para Business Server (no local)**|**Exchange 2010 (no local) + Skype para negócios Online**|**Exchange 2016/2013(on premises) + Skype para negócios Online**|**Exchange Online + Skype para negócios on-line**|
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
|Alta resolução fotos de contatos (requer o Lync 2013 ou Skype para clientes de negócios no mínimo. Não há suporte para LWA, aplicativos móveis, Lync 2010, Lync para Mac e outros clientes mais antigos).  <br/> |Sim (requer o Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |S  <br/> |S  <br/> |
|Delegação da reunião  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Perdidas histórico de conversas e Logs de chamada são gravados de correio do exchange do usuário  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |S  <br/> |
|Arquivamento de conteúdo (IM e reunião) no Exchange  <br/> |Sim (requer o Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Pesquise o conteúdo arquivado  <br/> |Sim (requer o Exchange 2016/2013)  <br/> |Y  <br/> |N  <br/> |N  <br/> |Y  <br/> |
|Caixa Postal UM do Exchange  <br/> |S  <br/> |S  <br/> |N  <br/> |N  <br/> |N  <br/> |
|Histórico da Conversa no Lado do Servidor  <br/> |Y  <br/> |S  <br/> |N  <br/> |S  <br/> |S  <br/> |

> [!NOTE]
> Há um serviço de correio de voz de nuvem que é suportado para Skype para Business Online, Skype para Business Server 2019, Skype para Business Server 2015 e Lync Server 2013.
> 

## <a name="see-also"></a>Consulte Também
<a name="feature_support"> </a>

[Configurar a integração entre o local Skype para Business Server e o Outlook Web App](../../deploy/integrate-with-exchange-server/outlook-web-app.md)
  
[Configurar OAuth entre o Skype for Business Online e o Exchange no local](../../deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises.md)

[Integrar Skype para Business Server com o Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
[Como integrar o Exchange Server 2013 com uma implantação do Lync Server 2013 híbrido, Skype para Business Online ou Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=746494)
  
[Configurar aplicativos de parceiros no Skype para Business Server e Microsoft Exchange Server](../../deploy/integrate-with-exchange-server/configure-partner-applications.md)
