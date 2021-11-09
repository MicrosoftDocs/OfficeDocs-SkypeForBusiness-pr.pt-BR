---
title: Configurar aplicativos parceiros no Skype for Business Server 2015 e Exchange Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 9c3a3054-6201-433f-b128-4c49d3341370
description: 'Resumo: Configure a autenticação de servidor para servidor Exchange Server 2016 ou Exchange Server 2013 e Skype for Business Server.'
ms.openlocfilehash: bb76b34bdf1a5a8a6c1b60fc200c46112985f31c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864238"
---
# <a name="configure-partner-applications-in-skype-for-business-server-and-exchange-server"></a>Configurar aplicativos parceiros em Skype for Business Server e Exchange Server
 
**Resumo:** Configure a autenticação de servidor para servidor Exchange Server 2016 ou Exchange Server 2013 e Skype for Business Server.
  
A autenticação de servidor para servidor geralmente requer dois servidores que precisam se comunicar entre si e um servidor de token de segurança de terceiros. Se o Servidor A e o Servidor B precisarem se comunicar, esses dois servidores geralmente começam contatando um servidor de tokens e obtendo um token de segurança mutuamente confiável. O Servidor A apresenta esse token de segurança ao Servidor B (e vice-versa) como uma maneira de garantir sua autenticidade e confiabilidade.
  
No entanto, esta é uma regra geral. Skype for Business Server, Exchange Server 2016, Exchange Server 2013 e SharePoint Server 2013 não precisam usar um servidor de token de terceiros ao se comunicarem entre si; isso porque esses produtos de servidor podem criar tokens de segurança que podem ser aceitos um pelo outro sem a necessidade de um servidor de token separado. (Esse recurso só está disponível no Skype for Business Server, Exchange Server 2016, Exchange Server 2013 e SharePoint Server 2013. Se você precisar configurar uma autenticação entre servidores com outros servidores, incluindo outros produtos de servidor da Microsoft, então será necessário fazer isso usando um terceiro servidor de token.
  
Para configurar a autenticação de servidor para servidor entre Skype for Business Server e Exchange Server você deve fazer duas coisas: 1) você deve atribuir os certificados apropriados a cada servidor; e, 2) você deve configurar cada servidor para ser um aplicativo parceiro do outro servidor: isso significa que você deve configurar o Skype for Business Server para ser um aplicativo parceiro para Exchange Server e configurar o Exchange Server para ser um aplicativo parceiro para Skype for Business Server.
  
## <a name="configuring-skype-for-business-server-to-be-a-partner-application-for-exchange-server"></a>Configurando Skype for Business Server ser um aplicativo de parceiro para Exchange Server

A maneira mais fácil de configurar o Skype for Business Server para ser um aplicativo parceiro com o Exchange Server 2016 ou o Exchange Server 2013 é executar o script Configure-EnterprisePartnerApplication.ps1, um script Windows PowerShell que acompanha Exchange Server. Para executar esse script, você deve fornecer a URL do documento de metadados Skype for Business Server autenticação; normalmente será o nome de domínio totalmente qualificado do pool Skype for Business Server seguido pelo sufixo /metadados/json/1. Por exemplo:
  
```console
https://atl-cs-001.litwareinc.com/metadata/json/1
```

Para configurar o Skype for Business Server como um aplicativo parceiro, abra o Shell de Gerenciamento do Exchange e execute um comando semelhante a este (supondo que o Exchange tenha sido instalado na unidade C: e que ele use o caminho de pasta padrão):
  
```powershell
"C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"
```

Depois de configurar o aplicativo parceiro, é recomendável que você pare e reinicie Serviços de Informações da Internet (IIS) em sua caixa de correio Exchange servidores de acesso para cliente. Você pode reiniciar o IIS usando um comando similar a este, que reinicia o serviço no computador atl-exchange-001:
  
```powershell
iisreset atl-exchange-001
```

Esse comando pode ser executado de dentro do Shell de Gerenciamento Exchange ou de qualquer outra janela de comando executado sob privilégios de administrador.
  
## <a name="configuring-exchange-server-to-be-a-partner-application-for-skype-for-business-server"></a>Configurando Exchange Server ser um aplicativo de parceiro para Skype for Business Server

Depois de configurar o Skype for Business Server para ser um aplicativo parceiro para o Exchange Server 2016 ou Exchange Server 2013, você deve configurar o Exchange Server para ser um aplicativo parceiro para Skype for Business Server. Isso pode ser feito usando o Shell de Gerenciamento Skype for Business Server e especificando o documento de metadados de autenticação para Exchange; normalmente será o URI do serviço Exchange descoberta automática seguido pelo sufixo /metadados/json/1. Por exemplo:
  
```console
https://autodiscover.litwareinc.com/autodiscover/metadata/json/1
```

No Skype for Business Server, os aplicativos parceiros são configurados usando o cmdlet [New-CsPartnerApplication.](/powershell/module/skype/new-cspartnerapplication?view=skype-ps) Além de especificar o URI de metadados, você também deve definir o nível de confiança do aplicativo como Completo; isso permitirá que Exchange represente a si mesmo e a qualquer usuário autorizado no reino. Por exemplo:
  
```powershell
New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
```

Como alternativa, você pode criar um aplicativo parceiro copiando e modificando o código de script encontrado na documentação Skype for Business Server autenticação servidor para servidor. Consulte o artigo Gerenciar autenticação de servidor para servidor [(OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) e aplicativos parceiros Skype for Business Server para obter mais informações.
  
Se você configurou com êxito aplicativos parceiros para Skype for Business Server e Exchange Server, também configurou com êxito a autenticação de servidor para servidor entre os dois produtos. Skype for Business Server inclui um cmdlet Windows PowerShell, [Test-CsExStorageConnectivity](/powershell/module/skype/test-csexstorageconnectivity?view=skype-ps) que permite verificar se a autenticação de servidor para servidor foi configurada corretamente e se a Skype for Business Server Armazenamento O serviço pode se conectar Exchange Server. O cmdlet faz isso conectando-se à caixa de correio de um usuário Exchange Server, escrevendo um item na pasta Histórico da Conversa para esse usuário e, em seguida, (opcionalmente) excluindo esse item.
  
Para testar a integração de Skype for Business Server e Exchange Server, execute um comando semelhante ao seguinte no Shell de Gerenciamento Skype for Business Server:
  
```powershell
Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"
```

No comando anterior, o SipUri representa o endereço SIP de um usuário com uma conta Exchange Server; seu comando falhará nesta não é uma conta de usuário válida.
  
> [!NOTE]
> Se você receber uma resposta 401 desse cmdlet, provavelmente será porque a configuração padrão para Exchange não inclui suporte para aceitar tokens Oauth. Para obter mais informações sobre como usar o Oauth no Exchange, consulte [Configure OAuth authentication with SharePoint 2013 and Skype for Business Server](/exchange/configure-oauth-authentication-with-sharepoint-2013-and-lync-2013-exchange-2013-help). 
  
Se o teste for bem sucedido e a conectividade for estabelecida, será possível então prosseguir para configurar recursos opcionais, como integração de arquivamento e o armazenamento de contato unificado.