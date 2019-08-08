---
title: Configurar as políticas de inicialização do cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Resumo: como gerenciar políticas de grupo.'
ms.openlocfilehash: 5d099a57db720a87e67ee00aa87a8613ac6552b7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234491"
---
# <a name="configure-client-bootstrapping-policies"></a>Configurar as políticas de inicialização do cliente
 
**Resumo:** Como gerenciar políticas de grupo.
  
O Console de Gerenciamento de Política de Grupo (GPMC) e o Editor de Objeto de Política de Grupo são ferramentas que você utiliza para gerenciar Políticas de Grupo. Incluído no modelo administrativo da política de grupo do Office, há modelos administrativos lync16. admx (ADMX) e. adml (ADML), que contêm as configurações de política baseadas no registro para o Skype for Business que você configura para objetos de política de grupo no domínio. Os arquivos ADML são complementos específicos de idioma para arquivos ADMX. Cada arquivo ADMX e ADML contém as configurações de política para um único aplicativo do Office. Você pode [baixar os arquivos de modelo administrativo do Office 2016 (admx/adml)](https://www.microsoft.com/en-us/download/details.aspx?id=49030) gratuitamente pelo centro de download da Microsoft.
  
Para clientes do Skype for Business, há várias políticas de inicialização do cliente que você deve considerar a configuração antes de os usuários entrarem no servidor pela primeira vez. Por exemplo, os servidores padrão e o modo de segurança que o cliente deve utilizar até que a entrada esteja concluída. Você pode usar a política de grupo para estabelecer essas configurações nos registros de computador dos usuários antes de entrarem e começar a receber as configurações de provisionamento em banda do servidor. A tabela a seguir lista as configurações de política de grupo que estão disponíveis para o Skype for Business.
  
**Configurações da política de grupo para o Skype for Business**

|Configuração de Política de Grupo|Descrição|
|:-----|:-----|
|Especificar servidor (ConfigurationMode)  <br/> | Especifica como o Skype for Business identifica o transporte e o servidor a serem usados durante a entrada. Com essa configuração, você especifica o seguinte: <br/>  ServerAddressExternal: Especifica o nome de servidor ou endereço IP utilizado pelos clientes e contatos federados ao se conectar de fora do firewall externo. <br/>  ServerAddressInternal: especifica o nome do servidor ou o endereço IP usado quando os clientes se conectam de dentro do firewall da organização. <br/>  Transport: Especifica o protocolo TCP ou protocolo TLS. <br/> |
|Versões adicionais do servidor com suporte (ConfiguredServerCheckValues)  <br/> |Especifica uma lista de nomes de versão do servidor separados por ponto-e-vírgulas que o Skype for Business Server fará logon, além das versões do servidor com suporte por padrão.  <br/> |
|Desativa o upload automático de logs de falha de assinatura (DisableAutomaticSendTracing)  <br/> |Carrega automaticamente os logs de falha de entrada no Skype for Business Server para análise. Nenhum log será carregado automaticamente se a entrada ocorrer com êxito. Se essa política não estiver configurada, ocorrerá o seguinte:  <br/> Para usuários do Skype for Business Online: logs de falha de entrada são carregados automaticamente. Para usuários do Skype for Business no local: uma caixa de diálogo de confirmação é exibida para o usuário antes do carregamento. Quando essa configuração estiver desabilitada, os logs de entrada serão carregados automaticamente para o Skype for Business Server para usuários do Skype for Business no local e no Skype for Business online. Quando essa configuração é habilitada, os logs de entrada nunca são carregados automaticamente.  <br/> |
|Desabilitar o fallback de HTTP para conexão SIP (DisableHttpConnect)  <br/> |Impede que o Skype for Business Server tente se conectar ao servidor usando HTTP, se TLS ou TCP não estiverem disponíveis. Por padrão, o Skype for Business primeiramente tenta se conectar ao servidor usando TLS ou TCP e, se nenhum desses métodos de transporte for bem-sucedido, o Skype for Business tentará se conectar usando HTTP. Use essa política para desabilitar a tentativa de conexão por HTTP de fallback.  <br/> |
|Exigir credenciais de logon (DisableNTCredentials)  <br/> |Requer que o usuário forneça credenciais de logon para o Skype for Business em vez de usar as credenciais do Windows automaticamente durante a conexão com um servidor SIP.  <br/> |
|Desabilitar a verificação de versão do servidor (DisableServerCheck)  <br/> |Se você definir essa política como 1, o Skype for Business não verifica o nome do servidor e a versão antes de entrar. Por padrão, o Skype for Business faz essas verificações antes de entrar.  <br/> |
|Habilitar o uso do BITS para baixar arquivos do serviço de catálogo de endereços (EnableBitsForGalDownload)  <br/> |Permite que o Skype for Business use o serviço de transferência inteligente em segundo plano (BITS) para baixar os arquivos dos serviços de catálogo de endereços.  <br/> |
|Configurar o modo de segurança SIP (EnableSIPHighSecurityMode)  <br/> |Permite que o Skype for Business envie e receba mensagens instantâneas com mais segurança. Essa política não tem efeito no Windows .NET, nem em serviços de Servidor do Microsoft Exchange.  <br/> Se você não definir essa configuração de política, o Skype for Business poderá usar qualquer transporte. Mas se ele não usar TLS e se o servidor autenticar usuários, o Skype for Business deverá usar a autenticação NTLM ou Kerberos.  <br/> |
|Atraso inicial do download do catálogo de endereços global (GalDownloadInitialDelay)  <br/> |Especifica o período de tempo antes de um download da lista de endereço global (GAL) ocorrer. O valor padrão é 60 minutos, o que significa que o download do arquivo GAL é atrasado para um período aleatório entre 0 e 60 minutos.  <br/> |
|Impedir que os usuários executem o Skype for Business (PreventRun)  <br/> |Impede que os usuários executem o Skype for Business. Você pode definir essa configuração de política na Configuração do Computador e na Configuração do Usuário, mas a configuração de política na Configuração do Computador tem precedência.  <br/> |
|Permitir armazenamento de senhas de usuários (SavePassword)  <br/> |Permite que o Skype for Business armazene senhas.  <br/> |
|Configurar o modo de compactação SIP (SipCompression)  <br/> |Especifica quando ativar a compressão do SIP. Por padrão, a compressão do SIP está ativada com base na velocidade do adaptador. Observe que configurar tal política pode causar um aumento no tempo de assinatura.  <br/> |
|Lista de domínios confiáveis (TrustModelData)  <br/> |Lista os domínios confiáveis que não correspondem ao prefixo do domínio SIP cliente.  <br/> |
   
As políticas configuradas no servidor têm precedência sobre as configurações de Política de Grupo e as opções de cliente configuradas pelo usuário. A tabela a seguir resume a ordem na qual as configurações têm precedência quando ocorre um conflito.
  
**Precedência das Políticas de Grupo**

|**Precedência**|**Local ou método da configuração**|
|:-----|:-----|
|1  <br/> |Provisionamento em banda do Skype for Business Server  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |A caixa de diálogo opções no Skype for Business  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Para definir configurações de política de grupo usando os arquivos de modelo administrativo do Skype for Business

1. Crie uma pasta de nível de raiz para inserir todos os arquivos ADMX de idioma neutro. Por exemplo, crie uma pasta raiz para o armazenamento central no controlador de domínio neste local:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Este procedimento presume que você deseja gerenciar diversos computadores no seu domínio. Neste caso, armazene os modelos em um repositório central na pasta Sysvol no controlador de domínio primário. Isso fornece uma localização de armazenamento central replicado para Modelos Administrativos. 
  
2. Crie uma subpasta para cada idioma que você usar. Essas subpastas vão conter os arquivos de recurso ADML específicos do idioma. Por exemplo, crie uma subpasta para United States English (EN-US) neste local:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

