---
title: Configurar aplicativos de parceiros no Skype for Business Server 2015 e no Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Resumo: configurar a autenticação do servidor para o Exchange Server 2016 ou o Exchange Server 2013 e o Skype for Business Server.'
ms.openlocfilehash: 9512d271b23f26afcb1ef6385a1a6dd5d513c948
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797072"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Configurar aplicativos de parceiros no Skype for Business Server e no Exchange Server
 
**Resumo:** Configurar a autenticação do servidor para o Exchange Server 2016 ou do Exchange Server 2013 e do Skype for Business Server.
  
A autenticação de servidor para servidor geralmente requer dois servidores, que precisam se comunicar entre si, e um terceiro servidor de token de segurança. Se o servidor A e o servidor B precisarem se comunicar, então ambos os servidores geralmente começam entrando em contato com um servidor de token e obtendo um token de segurança mutuamente confiável. O Servidor A então apresenta esse token de segurança ao Servidor B (e vice-versa), como uma forma de garantir autenticidade e confiabilidade.
  
No entanto, esta é uma regra geral. O Skype for Business Server, o Exchange Server 2016, o Exchange Server 2013 e o SharePoint Server 2013 não precisam usar um servidor de token de terceiros quando se comunicam uns com os outros; Isso porque esses produtos de servidor podem criar tokens de segurança que podem ser aceitos por um do outro, sem a necessidade de um servidor token separado. (Esse recurso só está disponível no Skype for Business Server, Exchange Server 2016, Exchange Server 2013 e SharePoint Server 2013. Se você precisar configurar uma autenticação entre servidores com outros servidores, incluindo outros produtos de servidor da Microsoft, então terá que fazer isso usando um terceiro servidor de token.)
  
Para configurar a autenticação de servidor para servidor entre o Skype for Business Server e o Exchange Server, você deve fazer duas coisas: 1) você deve atribuir os certificados apropriados a cada servidor; e 2) você deve configurar cada servidor para ser uma aplicação de parceiro do outro servidor: isso significa que você deve configurar o Skype for Business Server para ser um aplicativo de parceiro do Exchange Server e deve configurar o Exchange Server para ser um aplicativo de parceiro para o Skype para Business Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configurar o Skype for Business Server para ser um aplicativo parceiro para Exchange Server

A maneira mais fácil de configurar o Skype for Business Server para ser um aplicativo de parceiro com o Exchange Server 2016 ou o Exchange Server 2013 é executar o script Configure-EnterprisePartnerApplication. ps1, um script do Windows PowerShell fornecido com o Exchange Server. Para executar esse script, você deve fornecer a URL para o documento de metadados de autenticação do Skype for Business Server; Isso normalmente será o nome de domínio totalmente qualificado do pool do servidor do Skype for Business seguido do sufixo/Metadata/JSON/1. Por exemplo:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Para configurar o Skype for Business Server como um aplicativo de parceiro, abra o Shell de gerenciamento do Exchange e execute um comando semelhante a este (pressupondo que o Exchange tenha sido instalado na unidade C: e que ele use o caminho de pasta padrão):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Depois de configurar o aplicativo de parceiro, é recomendável parar e reiniciar os serviços de informações da Internet (IIS) em sua caixa de correio do Exchange e servidores de acesso para cliente. Você pode reiniciar o IIS usando um comando similar a esse, que reinicia o serviço no atl-exchange-001 do computador:
  
```powershell
iisreset atl-exchange-001
```

Esse comando pode ser executado no Shell de gerenciamento do Exchange ou em qualquer outra janela de comando executada em privilégios de administrador.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configurando o Exchange Server para ser um aplicativo parceiro para o Skype for Business Server

Depois de configurar o Skype for Business Server para ser um aplicativo parceiro para Exchange Server 2016 ou Exchange Server 2013, configure o Exchange Server para ser um aplicativo de parceiro do Skype for Business Server. Isso pode ser feito usando o Shell de gerenciamento do Skype for Business Server e especificando o documento de metadados de autenticação para o Exchange; Isso normalmente será o URI do serviço de descoberta automática do Exchange seguido pelo sufixo/Metadata/JSON/1. Por exemplo:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

No Skype for Business Server, os aplicativos de parceiros são configurados usando o cmdlet [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) . Além de especificar o URI dos metadados, você também deve definir o nível de confiança do aplicativo como Full; Isso permitirá que o Exchange represente tanto e qualquer usuário autorizado no território. Por exemplo:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Você também pode criar um aplicativo de parceiro copiando e modificando o código de script encontrado na documentação de autenticação do servidor para servidor do Skype for Business Server. Para obter mais informações, consulte o artigo [gerenciar autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Skype for Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) para obter mais informações.
  
Se você configurou com êxito aplicativos de parceiros para o Skype for Business Server e o Exchange Server, também configurou com êxito a autenticação de servidor para servidor entre os dois produtos. O Skype for Business Server inclui um cmdlet do Windows PowerShell, [teste-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) , que permite que você verifique se a autenticação de servidor-a-servidor foi configurada corretamente e se o serviço de armazenamento do Skype for Business Server pode se conectar ao Exchange Server. O cmdlet faz isso conectando-se à caixa de correio de um usuário do Exchange Server, escrevendo um item na pasta de histórico de conversas desse usuário e, em seguida, (opcionalmente) excluir esse item.
  
Para testar a integração do Skype for Business Server e do Exchange Server, execute um comando semelhante ao seguinte do Shell de gerenciamento do Skype for Business Server:
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

No comando anterior, o SipUri representa o endereço SIP de um usuário com uma conta no Exchange Server; seu comando falhará em uma conta de usuário válida.
  
> [!NOTE]
> Se você receber uma resposta 401 desse cmdlet, é provável que a configuração padrão do Exchange não inclua suporte para aceitar tokens OAuth. Para obter mais informações sobre como usar o OAuth no Exchange, consulte [Configurar a autenticação OAuth com o SharePoint 2013 e o Skype for Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103). 
  
Se o teste for bem sucedido e a conectividade for estabelecida, você poderá então prosseguir para configurar recursos opcionais, como integração de arquivamento e repositório de contato unificado.
