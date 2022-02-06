---
title: Configurar as políticas de inicialização do cliente
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 45042eca-b845-4207-b12f-b8b7f5d44bdf
description: 'Resumo: Como gerenciar políticas de grupo.'
---

# <a name="configure-client-bootstrapping-policies"></a>Configurar as políticas de inicialização do cliente
 
**Resumo:** Como gerenciar políticas de grupo.
  
O Console de Gerenciamento de Política de Grupo (GPMC) e o Editor de Objeto de Política de Grupo são ferramentas que você usa para gerenciar a Política de Grupo. Incluído no Modelo Administrativo de Política de Grupo do Office estão modelos administrativos lync16.admx (ADMX) e .adml (ADML), que contêm as configurações de política baseadas no Registro para Skype for Business que você configurar para objetos de Política de Grupo no domínio. Arquivos ADML são complementos específicos do idioma para arquivos ADMX. Cada arquivo ADMX e ADML contém as configurações de política para um único Office aplicativo. Você pode [baixar os arquivos de modelo administrativo do Office 2016 (ADMX/ADML)](https://www.microsoft.com/download/details.aspx?id=49030) gratuitamente no Centro de Download da Microsoft.
  
Para Skype for Business clientes, há várias políticas de inicialização de cliente que você deve considerar configurar antes que os usuários entre no servidor pela primeira vez. Por exemplo, os servidores padrão e o modo de segurança que o cliente deve usar até que a entrada seja concluída. Você pode usar a Política de Grupo para estabelecer essas configurações nos registros do computador dos usuários antes de entrar e começar a receber configurações de provisionamento em banda do servidor. A tabela a seguir lista as configurações da Política de Grupo disponíveis para Skype for Business.
  
**Política de Grupo Configurações para Skype for Business**

|Configuração da Política de grupo|Descrição|
|:-----|:-----|
|Especificar Servidor (ConfigurationMode)  <br/> | Especifica como o Skype for Business identifica o transporte e o servidor a ser usado durante a assinatura. Nesta configuração, especifique o seguinte: <br/>  ServerAddressExternal: Especifica o nome do servidor ou endereço IP usado por clientes e contatos federados ao se conectar de fora do firewall externo. <br/>  ServerAddressInternal: Especifica o nome do servidor ou endereço IP usado quando os clientes se conectam de dentro do firewall da organização. <br/>  Transporte: especifica TCP (Protocolo de Controle de Transmissão) ou Segurança da Camada de Transporte (TLS). <br/> |
|Versões adicionais de servidor com suporte (ConfiguredServerCheckValues)  <br/> |Especifica uma lista de nomes de versão do servidor separados por pontos-e-vírgulas que Skype for Business Server logoff, além das versões do servidor com suporte por padrão.  <br/> |
|Desabilitar o carregamento automático de logs de falha de login (DisableAutomaticSendTracing)  <br/> |Carrega automaticamente logs de falha de Skype for Business Server para análise. Nenhum logs será carregado automaticamente se a conexão for bem-sucedida. Se essa política não estiver configurada, o seguinte ocorrerá:  <br/> Para Skype for Business online: os logs de falha de login são carregados automaticamente. Para Skype for Business usuários locais: uma caixa de diálogo de confirmação é mostrada ao usuário antes de carregar. Quando essa configuração é desabilitada, os logs de login são carregados automaticamente no Skype for Business Server para usuários Skype for Business locais e Skype for Business Online. Quando essa configuração está habilitada, os logs de login nunca são carregados automaticamente.  <br/> |
|Desabilitar o fallback HTTP para conexão SIP (DisableHttpConnect)  <br/> |Impede Skype for Business Server tentar se conectar ao servidor usando HTTP, se TLS ou TCP não estiver disponível. Por padrão, Skype for Business tenta se conectar ao servidor usando TLS ou TCP e, se nenhum desses métodos de transporte for bem-sucedido, Skype for Business tenta se conectar usando HTTP. Use essa política para desabilitar a tentativa de conexão HTTP de fallback.  <br/> |
|Exigir credenciais de logon (DisableNTCredentials)  <br/> |Exige que o usuário forneça credenciais de logon para Skype for Business em vez de usar automaticamente Windows credenciais durante a login em um servidor SIP.  <br/> |
|Desabilitar a verificação de versão do servidor (DisableServerCheck)  <br/> |Se você definir essa política como 1, impedirá Skype for Business verificar o nome e a versão do servidor antes de entrar. Por padrão, Skype for Business faz essas verificações antes de entrar.  <br/> |
|Habilitar o uso de BITS para baixar arquivos do Serviço de Livro de Endereços (EnableBitsForGalDownload)  <br/> |Permite Skype for Business usar BITS (Serviço de Transferência Inteligente em Segundo Plano) para baixar os arquivos dos Serviços do Livro de Endereços.  <br/> |
|Configurar o modo de segurança SIP (EnableSIPHighSecurityMode)  <br/> |Permite Skype for Business enviar e receber mensagens instantâneas com mais segurança. Essa política não tem efeito sobre os serviços .NET ou Microsoft Exchange Server do Windows.  <br/> Se você não definir essa configuração de política, Skype for Business pode usar qualquer transporte. Mas se ele não usar TLS e se o servidor autenticar usuários, Skype for Business deve usar a autenticação NTLM ou Kerberos.  <br/> |
|Atraso inicial do download do Livro de Endereços Global (GalDownloadInitialDelay)  <br/> |Especifica o período de tempo antes de ocorrer um download da gal (lista de endereços global). O valor padrão é 60 minutos, o que significa que o servidor atrasa o download do arquivo GAL por um período aleatório entre 0 e 60 minutos.  <br/> |
|Impedir que os usuários Skype for Business (PreventRun)  <br/> |Impede que os usuários executam Skype for Business. Você pode configurar essa definição de diretiva em Configuração do Computador e em Configuração do Usuário, mas a definição de Configuração do Computador tem precedência.  <br/> |
|Permitir armazenamento de senhas de usuário (SavePassword)  <br/> |Permite Skype for Business armazenar senhas.  <br/> |
|Configurar o modo de compactação SIP (SipCompression)  <br/> |Especifica quando ativar a compactação SIP. Por padrão, a compactação SIP é habilitada com base na velocidade do adaptador. Observe que a configuração dessa política pode causar um aumento no tempo de login.  <br/> |
|Lista de domínios confiáveis (TrustModelData)  <br/> |Lista os domínios confiáveis que não corresponderem ao prefixo do domínio SIP do cliente.  <br/> |
   
As políticas configuradas no servidor têm precedência sobre as configurações de Política de Grupo e as opções de cliente configuradas pelo usuário. A tabela a seguir resume a ordem na qual as configurações têm precedência quando ocorre um conflito.
  
**Precedência das Políticas de Grupo**

|**Precedence**|**Local ou método da configuração**|
|:-----|:-----|
|1  <br/> |Skype for Business Server provisionamento em banda  <br/> |
|2  <br/> |HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|3  <br/> |HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Lync  <br/> |
|4  <br/> |A caixa de diálogo Opções no Skype for Business  <br/> |
   
### <a name="to-define-group-policy-settings-by-using-the-skype-for-business-administrative-template-files"></a>Para definir as configurações da Política de Grupo usando os arquivos Skype for Business de modelo administrativo

1. Crie uma pasta de nível raiz para conter todos os arquivos ADMX neutros do idioma. Por exemplo, crie a pasta raiz do repositório central em seu controlador de domínio neste local:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions`
    
    > [!NOTE]
    > Este procedimento supõe que você deseja gerenciar vários computadores em seu domínio. Nesse caso, você armazena os modelos em um armazenamento central na pasta Sysvol no controlador de domínio principal. Isso oferece um local de repositório central para Modelos Administrativos do domínio. 
  
2. Crie uma subpasta para cada idioma que você usará. Essas subpastas conterão os arquivos de recurso ADML específicos do idioma. Por exemplo, crie uma subpasta para inglês dos Estados Unidos (EN-US) neste local:
    
     `%systemroot%\sysvol\domain\policies\PolicyDefinitions\EN-US`
    

