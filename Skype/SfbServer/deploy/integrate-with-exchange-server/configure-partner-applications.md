---
title: Configurar aplicativos parceiros no Skype for Business Server 2015 e no Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: Configure a autenticação de servidor para servidor para o Exchange Server 2016 ou Exchange Server 2013 e o Skype for Business Server.'
ms.openlocfilehash: a707836a43965f477dc037f71bb68cbda8c8e96c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834041"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Configurar aplicativos parceiros no Skype for Business Server e no Exchange Server
 
**Resumo:** Configure a autenticação de servidor para servidor para Exchange Server 2016 ou Exchange Server 2013 e Skype for Business Server.
  
A autenticação de servidor para servidor geralmente requer dois servidores que precisam se comunicar entre si e com um servidor de token de segurança de terceiros. Se o Servidor A e o Servidor B precisam se comunicar, então ambos geralmente começam contatando um servidor de token e obtendo um token de segurança mutuamente confiável. Em seguida, o Servidor A apresenta esse token de segurança ao Servidor B (e vice-versa) como uma maneira de garantir sua autenticidade e confiabilidade.
  
No entanto, esta é uma regra geral. O Skype for Business Server, o Exchange Server 2016, o Exchange Server 2013 e o SharePoint Server 2013 não precisam usar um servidor de token de terceiros ao se comunicarem entre si; isso porque esses produtos de servidor podem criar tokens de segurança que podem ser aceitos um pelo outro sem a necessidade de um servidor de token separado. (Esse recurso só está disponível no Skype for Business Server, Exchange Server 2016, Exchange Server 2013 e SharePoint Server 2013. Se você precisar configurar uma autenticação entre servidores com outros servidores, incluindo outros produtos de servidor da Microsoft, então será necessário fazer isso usando um terceiro servidor de token.
  
Para configurar a autenticação de servidor para servidor entre o Skype for Business Server e o Exchange Server, você deve fazer duas coisas: 1) você deve atribuir os certificados apropriados a cada servidor; e, 2) você deve configurar cada servidor para ser um aplicativo parceiro do outro servidor: isso significa que você deve configurar o Skype for Business Server para ser um aplicativo parceiro do Exchange Server e deve configurar o Exchange Server para ser um aplicativo parceiro do Skype for Business Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configurando o Skype for Business Server para ser um aplicativo parceiro para o Exchange Server

A maneira mais fácil de configurar o Skype for Business Server para ser um aplicativo parceiro com o Exchange Server 2016 ou o Exchange Server 2013 é executar o script Configure-EnterprisePartnerApplication.ps1, um script do Windows PowerShell que acompanha o Exchange Server. Para executar esse script, você deve fornecer a URL do documento de metadados de autenticação do Skype for Business Server; normalmente será o nome de domínio totalmente qualificado do pool do Skype for Business Server seguido pelo sufixo /metadata/json/1. Por exemplo:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Para configurar o Skype for Business Server como um aplicativo parceiro, abra o Shell de Gerenciamento do Exchange e execute um comando semelhante a este (supondo que o Exchange tenha sido instalado na unidade C: e que ele use o caminho da pasta padrão):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Depois de configurar o aplicativo parceiro, é recomendável que você pare e reinicie os Serviços de Informações da Internet (IIS) em sua caixa de correio do Exchange e servidores de acesso para cliente. Você pode reiniciar o IIS usando um comando similar a este, que reinicia o serviço no computador atl-exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Esse comando pode ser executado de dentro do Shell de Gerenciamento do Exchange ou de qualquer outra janela de comando que seja executado sob privilégios de administrador.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configurando o Exchange Server para ser um aplicativo parceiro do Skype for Business Server

Depois de configurar o Skype for Business Server para ser um aplicativo parceiro para o Exchange Server 2016 ou o Exchange Server 2013, você deve configurar o Exchange Server para ser um aplicativo parceiro do Skype for Business Server. Isso pode ser feito usando o Shell de Gerenciamento do Skype for Business Server e especificando o documento de metadados de autenticação para o Exchange; normalmente será o URI do serviço de descoberta automática do Exchange seguido pelo sufixo /metadata/json/1. Por exemplo:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

No Skype for Business Server, os aplicativos parceiros são configurados usando o cmdlet [New-CsPartnerApplication.](https://docs.microsoft.com/powershell/module/skype/new-cspartnerapplication?view=skype-ps) Além de especificar o URI de metadados, você também deve definir o nível de confiança do aplicativo como Completo; isso permitirá que o Exchange represente o próprio usuário autorizado no realm. Por exemplo:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Como alternativa, você pode criar um aplicativo parceiro copiando e modificando o código de script encontrado na documentação de autenticação de servidor para servidor do Skype for Business Server. Consulte o artigo Gerenciar autenticação de servidor para servidor [(OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) e aplicativos parceiros no Skype for Business Server para obter mais informações.
  
Se você configurou com êxito aplicativos parceiros para o Skype for Business Server e o Exchange Server, você também configurou com êxito a autenticação de servidor para servidor entre os dois produtos. O Skype for Business Server inclui um cmdlet do Windows PowerShell, [Test-CsExStorageConnectivity,](https://docs.microsoft.com/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) que permite verificar se a autenticação de servidor para servidor foi configurada corretamente e se o Serviço de Armazenamento do Skype for Business Server pode se conectar ao Exchange Server. O cmdlet faz isso conectando-se à caixa de correio de um usuário do Exchange Server, escrevendo um item na pasta Histórico da Conversa desse usuário e, opcionalmente, excluindo esse item.
  
Para testar a integração do Skype for Business Server e do Exchange Server, execute um comando semelhante ao seguinte do Shell de Gerenciamento do Skype for Business Server:
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

No comando anterior, o SipUri representa o endereço SIP de um usuário com uma conta no Exchange Server; o comando falhará se não for uma conta de usuário válida.
  
> [!NOTE]
> Se você receber uma resposta 401 desse cmdlet, provavelmente é porque a configuração padrão do Exchange não inclui suporte para aceitar tokens Oauth. Para obter mais informações sobre como usar o Oauth no Exchange, consulte Configurar a autenticação [OAuth com o SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=513103)e o Skype for Business Server. 
  
Se o teste for bem sucedido e a conectividade for estabelecida, será possível então prosseguir para configurar recursos opcionais, como integração de arquivamento e o armazenamento de contato unificado.
