---
title: Configurar aplicativos de parceiros no Skype para Business Server 2015 e o Exchange Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Resumo: Configure a autenticação de servidor para servidor para o Exchange Server 2016 ou Exchange Server 2013 e Skype para Business Server.'
ms.openlocfilehash: f437b081466f837c012e0d2ddba8bea79d3ad445
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973077"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Configurar aplicativos de parceiros no Skype para Business Server e o Exchange Server
 
**Resumo:** Configure a autenticação de servidor para servidor para o Exchange Server 2016 ou Exchange Server 2013 e Skype para Business Server.
  
A autenticação de servidor para servidor geralmente requer dois servidores, que precisam se comunicar entre si, e um terceiro servidor de token de segurança. Se o servidor A e servidor B precisam se comunicar, ambos desses servidores normalmente inicie navegando entrando em contato com um servidor de token e como obter um token de segurança mutuamente confiáveis. O Servidor A então apresenta esse token de segurança ao Servidor B (e vice-versa), como uma forma de garantir autenticidade e confiabilidade.
  
No entanto, esta é uma regra geral. Skype para Business Server, Exchange Server 2016, Exchange Server 2013 e SharePoint Server 2013 não é necessário usar um servidor de token de terceiros ao se comunicar umas com as outras; Isso acontece porque esses produtos de servidor podem criar tokens de segurança que podem ser aceita pelo entre si sem a necessidade de um servidor de token separado. (Esse recurso só está disponível no Skype para Business Server, Exchange Server 2016, Exchange Server 2013 e SharePoint Server 2013. Se você precisar configurar uma autenticação entre servidores com outros servidores, incluindo outros produtos de servidor da Microsoft, então terá que fazer isso usando um terceiro servidor de token.)
  
Para configurar a autenticação de servidor-para-servidor entre Skype para Business Server e o Exchange Server, você deve fazer duas coisas: 1) você deve atribuir os certificados apropriados a cada servidor; e, 2) você deve configurar cada servidor para ser um aplicativo de parceiro do servidor do: isso significa que você deve configurar Skype para Business Server seja um aplicativo parceiro do Exchange Server e você deverá configurar o Exchange Server para ser um aplicativo parceiro do Skype para o servidor de negócios.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configurando o Skype para Business Server seja um aplicativo parceiro do Exchange Server

A maneira mais fácil de configurar Skype para Business Server seja um aplicativo parceiro com o Exchange Server 2016 ou Exchange Server 2013 é executar o script Configure-EnterprisePartnerApplication.ps1, um script do Windows PowerShell que acompanha o Exchange Server. Para executar esse script, você deve fornecer a URL para o Skype para o documento de metadados de autenticação Business Server; Normalmente, esse será o nome de domínio totalmente qualificado do Skype para pool de servidores de negócios, seguido por /metadata/json/1 o sufixo. Por exemplo:
  
```
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Para configurar o Skype para Business Server como um aplicativo de parceiro, abra o Shell de gerenciamento do Exchange e execute um comando semelhante ao seguinte (supondo que o Exchange foi instalado na unidade c: e que ele usa o caminho da pasta padrão):
  
```
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Depois de configurar o aplicativo parceiro é recomendável que você parar e reiniciar os serviços de informações da Internet (IIS) em seus servidores de acesso de cliente e caixa de correio do Exchange. Você pode reiniciar o IIS usando um comando similar a esse, que reinicia o serviço no atl-exchange-001 do computador:
  
```
iisreset atl-exchange-001
```

Este comando pode ser executado de dentro do Shell de gerenciamento do Exchange ou de qualquer outra janela de comando executados sob privilégios de administrador.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configurando o Exchange Server para ser um aplicativo parceiro do Skype para Business Server

Depois de ter configurado Skype para Business Server seja um aplicativo parceiro do Exchange Server 2016 ou Exchange Server 2013, você deve, em seguida, configure o Exchange Server para ser um aplicativo parceiro do Skype para Business Server. Isso pode ser feito usando o Skype do Shell de gerenciamento do servidor de negócios e especificando o documento de metadados de autenticação para o Exchange; Normalmente, esse será o URI do serviço de descoberta automática do Exchange seguido /metadata/json/1 o sufixo. Por exemplo:
  
```
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

Skype para Business Server, aplicativos de parceiros são configurados usando o cmdlet [New-CsPartnerApplication](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) . Além de especificar o URI de metadados você deve também definir a relação de confiança do aplicativo nível como Full; Isso permitirá que o Exchange representar a mesmo e qualquer usuário autorizado no realm. Por exemplo:
  
```
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Como alternativa, você pode criar um aplicativo de parceiro ao copiar e modificar o código de script encontrado no Skype para documentação de autenticação de servidor-para-servidor Business Server. Consulte o artigo de [gerenciar autenticação de servidor-para-servidor (OAuth) e aplicativos de parceiros no Skype para Business Server](../../manage/authentication/server-to-server-and-partner-applications.md) para obter mais informações.
  
Se você configurou com êxito aplicativos de parceiros para ambos os Skype para Business Server e o Exchange Server, você configurou com êxito a autenticação de servidor-para-servidor entre os dois produtos. Skype para Business Server inclui um cmdlet do Windows PowerShell, [Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) que permite verificar que se a autenticação servidor-para-servidor foi configurada corretamente e que o Skype para serviço de armazenamento do servidor de negócios pode Conecte ao servidor do Exchange. O cmdlet faz isso conectando-se à caixa de correio de um usuário do Exchange Server, escrevendo um item na pasta Histórico da conversa para esse usuário e, em seguida, excluindo (opcionalmente) que o item.
  
Para testar a integração do Skype para Business Server e o Exchange Server, execute um comando semelhante ao seguinte a partir do Skype do Shell de gerenciamento do servidor de negócios:
  
```
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

No comando anterior, o SipUri representa o endereço SIP de um usuário com uma conta no servidor do Exchange; o comando irá falhar nisso não é uma conta de usuário válido.
  
> [!NOTE]
> Se você receber uma resposta 401 desse cmdlet, provavelmente é porque a configuração padrão para o Exchange não inclui suporte para aceitar tokens Oauth. Para obter mais informações sobre como usar Oauth no Exchange, consulte [Configure OAuth authentication com o SharePoint 2013 e Skype para Business Server](https://go.microsoft.com/fwlink/p/?LinkId=513103). 
  
Se o teste for bem sucedido e a conectividade for estabelecida, você poderá então prosseguir para configurar recursos opcionais, como integração de arquivamento e repositório de contato unificado.