---
title: Configurar as políticas de inicialização do cliente
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Resumo: Como gerenciar as políticas de grupo.'
ms.openlocfilehash: b2652b42b58767aecd3556224b869211eb7e7a27
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885847"
---
# <a name="configure-client-bootstrapping-policies"></a>Configurar as políticas de inicialização do cliente
 
**Resumo:** Como gerenciar políticas de grupo.
  
O Console de Gerenciamento de Política de Grupo (GPMC) e o Editor de Objeto de Política de Grupo são ferramentas que você utiliza para gerenciar Políticas de Grupo. Estão incluídos com o modelo administrativo de diretiva de grupo Office lync16.admx (ADMX) e os modelos administrativos. adml (ADML), que contêm as configurações de diretiva baseadas no registro para Skype for Business que você configurar para objetos de diretiva de grupo no domínio. Os arquivos ADML são complementos específicos de idioma para arquivos ADMX. Cada arquivo ADMX e ADML contém as configurações de política para um único aplicativo do Office. Você pode [baixar os arquivos de modelo administrativo do Office 2016 (ADMX/ADML)](https://www.microsoft.com/en-us/download/details.aspx?id=49030) gratuitamente do Microsoft Download Center.
  
Para Skype para clientes corporativos, há várias client bootstrapping políticas que você deve considerar Configurando antes que os usuários fazem logon servidor pela primeira vez. Por exemplo, os servidores padrão e o modo de segurança que o cliente deve utilizar até que a entrada esteja concluída. Você pode usar a diretiva de grupo para estabelecer essas configurações nos registros de computador dos usuários antes de entrar e começar a receber as configurações de provisionamento em banda do servidor. A tabela a seguir lista as configurações de diretiva de grupo disponíveis para Skype para negócios.
  
**Configurações de diretiva de grupo para Skype para negócios**

|Configuração de Política de Grupo|Descrição|
|:-----|:-----|
|Especificar servidor (ConfigurationMode)  <br/> | Especifica como o Skype para negócios identifica o transporte e o servidor a ser usado durante a entrada. Com essa configuração, você especifica o seguinte: <br/>  ServerAddressExternal: Especifica o nome de servidor ou endereço IP utilizado pelos clientes e contatos federados ao se conectar de fora do firewall externo. <br/>  ServerAddressInternal: Especifica o nome do servidor ou o endereço IP usado quando os clientes se conectam de dentro do firewall da organização. <br/>  Transport: Especifica o protocolo TCP ou protocolo TLS. <br/> |
|Versões de servidor adicionais suportadas (ConfiguredServerCheckValues)  <br/> |Especifica uma lista dos nomes de versão do servidor separados por ponto e vírgula Skype para Business Server fará logon, além das versões de servidor suportadas por padrão.  <br/> |
|Desativa o upload automático de logs de falha de assinatura (DisableAutomaticSendTracing)  <br/> |Carrega automaticamente os logs de falha de entrada para Skype para Business Server para análise. Nenhum log será carregado automaticamente se a entrada ocorrer com êxito. Se essa política não estiver configurada, ocorrerá o seguinte:  <br/> Para Skype para usuários corporativos Online: entrar logs de falha são enviados automaticamente. Para Skype for Business usuários local: uma caixa de diálogo de confirmação é mostrada ao usuário antes do carregamento. Quando essa configuração estiver desativada, os logs de entrada são enviados automaticamente para o Skype para Business Server do Skype para negócios local e Skype para usuários corporativos Online. Quando essa configuração é habilitada, os logs de entrada nunca são carregados automaticamente.  <br/> |
|Desabilitar fallback de HTTP para conexão SIP (DisableHttpConnect)  <br/> |Impede que o Skype para Business Server tenta se conectar ao servidor usando o HTTP, se o TLS ou TCP não está disponível. Por padrão, Skype para negócios primeiro tenta se conectar ao servidor usando o TLS ou TCP e, se nenhum desses métodos de transporte for bem-sucedida, Skype para negócios tenta se conectar usando HTTP. Use essa política para desabilitar a tentativa de conexão por HTTP de fallback.  <br/> |
|Requer credenciais de login (DisableNTCredentials)  <br/> |Requer que o usuário forneça credenciais de logon para Skype para negócios em vez de usar automaticamente as credenciais do Windows durante o login em um servidor SIP.  <br/> |
|Desabilitar a verificação de versão do servidor (DisableServerCheck)  <br/> |Se você definir essa diretiva como 1, impede que Skype para negócios verificando o nome do servidor e a versão antes de entrar no. Por padrão, o Skype para negócios torna pelas verificações antes de entrar no.  <br/> |
|Habilitar o uso de BITS para baixar arquivos do serviço de catálogo de endereços (EnableBitsForGalDownload)  <br/> |Permite Skype for Business usar o serviço de transferência inteligente de plano de fundo (BITS) para baixar os arquivos do serviço Catálogo de endereços.  <br/> |
|Configurar o modo de segurança do SIP (EnableSIPHighSecurityMode)  <br/> |Permite Skype for Business enviar e receber mensagens instantâneas com mais segurança. Essa política não tem efeito no Windows .NET, nem em serviços de Servidor do Microsoft Exchange.  <br/> Se você não configurar essa definição de diretiva, Skype para a empresa pode usar qualquer transporte. Mas, se ele não usa TLS e se o servidor autenticar usuários, Skype para negócios deve usam a autenticação NTLM ou Kerberos.  <br/> |
|Atraso inicial (GalDownloadInitialDelay) de Download do catálogo de endereços global  <br/> |Especifica o período de tempo antes de um download da lista de endereço global (GAL) ocorrer. O valor padrão é 60 minutos, o que significa que o download do arquivo GAL é atrasado para um período aleatório entre 0 e 60 minutos.  <br/> |
|Evita que usuários executem Skype para negócios (PreventRun)  <br/> |Impede que os usuários executem Skype para negócios. Você pode definir essa configuração de política na Configuração do Computador e na Configuração do Usuário, mas a configuração de política na Configuração do Computador tem precedência.  <br/> |
|Permitir o armazenamento de senhas de usuário (SavePassword)  <br/> |Habilita o Skype para negócios a armazenar senhas.  <br/> |
|Configurar o modo de compactação SIP (SipCompression)  <br/> |Especifica quando ativar a compressão do SIP. Por padrão, a compressão do SIP está ativada com base na velocidade do adaptador. Observe que configurar tal política pode causar um aumento no tempo de assinatura.  <br/> |
|Lista de domínio confiável (TrustModelData)  <br/> |Lista os domínios confiáveis que não correspondem ao prefixo do domínio SIP cliente.  <br/> |
   
As políticas configuradas no servidor têm precedência sobre as configurações de Política de Grupo e as opções de cliente configuradas pelo usuário. A tabela a seguir resume a ordem na qual as configurações têm precedência quando ocorre um conflito.
  
**Precedência das Políticas de Grupo**

|**Precedência**|**Local ou método da configuração**|
|:-----|:-----|
|1  <br/> |Skype para provisionamento em banda do Business Server  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |A caixa de diálogo Opções no Skype para negócios  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Para definir as configurações de diretiva de grupo usando o Skype para arquivos de modelo administrativo de negócios

1. Crie uma pasta de nível de raiz para inserir todos os arquivos ADMX de idioma neutro. Por exemplo, crie uma pasta raiz para o armazenamento central no controlador de domínio neste local:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Este procedimento presume que você deseja gerenciar diversos computadores no seu domínio. Neste caso, armazene os modelos em um repositório central na pasta Sysvol no controlador de domínio primário. Isso fornece uma localização de armazenamento central replicado para Modelos Administrativos. 
  
2. Crie uma subpasta para cada idioma que você usará. Essas subpastas vão conter os arquivos de recurso ADML específicos do idioma. Por exemplo, crie uma subpasta para United States English (EN-US) neste local:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

