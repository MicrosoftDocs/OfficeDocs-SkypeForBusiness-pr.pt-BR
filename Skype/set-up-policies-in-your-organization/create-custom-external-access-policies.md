---
title: "Criar políticas de acesso externo personalizado"
ms.author: tonysmit
author: tonysmit
ms.date: 11/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
description: "Skype for Business Online permite que você criar políticas de acesso externo adicionais. Ao contrário de políticas de cliente ou de conferência, onde você pode ter várias combinações, há três políticas de acesso externo predefinido que podem abranger a maioria dos cenários. Estas são:"
---

# Criar políticas de acesso externo personalizado

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](89cbd278-5480-473c-8cd9-04e07e5f9e0b.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/89cbd278-5480-473c-8cd9-04e07e5f9e0b). 
  
Skype for Business Online permite que você criar políticas de acesso externo adicionais. Ao contrário de políticas de cliente ou de conferência, onde você pode ter várias combinações, há três políticas de acesso externo predefinido que podem abranger a maioria dos cenários. Estas são:
  
- Não federado ou acesso de consumidor do Skype ( _Tag:NoFederationAndPIC_ )
    
- Somente acesso federado ( _Tag:FederationOnly_ )
    
- Federado e consumidor acessar ( _FederationAndPICDefault_)
    
Políticas de externas personalizadas permitem criar adicionais políticas que não estão cobertos por configurações acima. Quando a política foi criada, você seria necessárias para definir todos os parâmetros necessários e não foi possível alterá-los posteriormente. Criar novas políticas personalizadas permitem aos recursos de controle como o access de consumidor do Skype ou uma política para desabilitar o público nuvem áudio/vídeo, que é algo que não foi coberto com configurações predefinidas. Políticas de acesso externo personalizado siga a mesma sintaxe políticas de cliente, mobilidade e conferências. Você pode encontrar mais informações sobre essas configurações [aqui](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Para que isso funcione, o usuário deve estar usando uma versão compatível do 2016 Skype do clique para executar de aplicativo de negócios que dá suporte a ele. A seguinte versão mínima do Skype para o cliente de negócios 2016 clique para executar é necessária:
  
|**Tipo**|**Data do lançamento**|**Versão**|**Build**|
|:-----|:-----|:-----|:-----|
|Primeiro Lançamento do Canal Atual  <br/> |17/11/2016  <br/> |16.0.7571.2006  <br/> |Versão 1611 (Build 7571.2006)  <br/> |
|Canal Atual  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Versão 1611 (build 7571.2072)  <br/> |
|Canal Adiado  <br/> |22/2/2017  <br/> |16.0.7369.2118  <br/> |Versão 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Os usuários que estão usando versões mais antigas do Skype para aplicativos de negócios Windows ou clientes de Mac ainda poderão transferir arquivos. 
  
## Verificar e iniciar o Windows PowerShell

- **Verifique se está executando o Windows PowerShell 3.0 ou versão superior**
    
1. Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.
    
2. Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.
    
3. Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.
    
4. Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.
    
    Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Iniciar uma sessão do Windows PowerShell**
    
1. No **Menu Iniciar** > **Windows PowerShell**.
    
2. Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:
    
    > [!NOTE]
    > Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

    Confira mais informações sobre como iniciar o Windows PowerShell em [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou[Conectar-se ao Skype for Business Online usando o Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
    
## Criar uma política de acesso externo personalizado para um usuário

Para fazer isso, execute:
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True 
-EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
  ```

## Quer saber mais sobre o Windows PowerShell?

- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos para usar o Windows PowerShell para gerenciar o Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

