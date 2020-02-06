---
title: Testar o AV e os certificados OAuth no Skype for Business Server usando-roll in Set-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Resumo: testar o AV e certificados OAuth para o Skype for Business Server.'
ms.openlocfilehash: 530e8f603d2c5be368df37354c3974e2b5abeb5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818723"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Testar o AV e os certificados OAuth no Skype for Business Server usando-roll in Set-CsCertificate
 
**Resumo:** Testar o AV e certificados OAuth para o Skype for Business Server.
  
As comunicações de áudio/vídeo (A/V) são um componente principal do Skype for Business Server. Recursos como compartilhamento de aplicativos e áudio e videoconferências dependem dos certificados atribuídos ao serviço de borda a/V, especificamente para o serviço de autenticação A/V.
  
> [!IMPORTANT]
> Este novo recurso foi projetado para funcionar para o serviço de borda a/V e para o certificado OAuthTokenIssuer. Outros tipos de certificados podem ser provisionados juntamente com o serviço de borda A/V e o tipo de certificado OAuth, mas não se beneficiarão do comportamento de coexistência que o certificado de serviço de borda A/V usará.
  
Os cmdlets do PowerShell do Shell de gerenciamento do Skype for Business Server usados para gerenciar certificados do Skype for Business Server referem-se ao certificado de serviço de borda a/V como o tipo de certificado AudioVideoAuthentication e o certificado OAuthServer como typeOAuthTokenIssuer. Para o restante deste tópico e para identificar os certificados com exclusividade, eles serão referidos pelo mesmo tipo de identificador, AudioVideoAuthentication andOAuthTokenIssuer.
  
O serviço de Autenticação A/V é responsável por emitir tokens que são usados por clientes e outros consumidores A/V. Os tokens são gerados de atributos no certificado e, quando o certificado expira, a perda de conexão e o requisito para participar novamente com um novo token gerado pelo novo certificado resultará. Um novo recurso no Skype for Business Server amenizará esse problema-a capacidade de testar um novo certificado antes do antigo expirar e permitir que os dois certificados continuem a funcionar por um período de tempo. Esse recurso usa a funcionalidade atualizada no cmdlet do Shell de gerenciamento do Skype for Business Server Set-CsCertificate. O novo parâmetro-roll, com o parâmetro existente-EffectiveDate irá colocar o novo certificado AudioVideoAuthentication no repositório de certificados. O certificado AudioVideoAuthentication mais antigo permanecerá para tokens emitidos serem validados. Começando a colocar o novo certificado AudioVideoAuthentication, a seguinte série de eventos ocorrerá:
  
> [!TIP]
> Usando os cmdlets do Shell de gerenciamento do Skype for Business Server para gerenciar certificados, você pode solicitar certificados separados e distintos para cada finalidade no servidor de borda. Usar o assistente de certificado no assistente de implantação do Skype for Business Server ajuda você a criar certificados, mas geralmente é do tipo **padrão** que associa todos os usos de certificado para o servidor de borda em um único certificado. A prática recomendada se você usar o recurso de agrupamento de certificado é desagrupar o certificado AudioVideoAuthentication de outros objetivos. É possível provisionar e dividir um certificado do tipo Padrão, mas apenas a parte do AudioVideoAuthentication do certificado combinado será beneficiada da separação. Um usuário envolvido (por exemplo) uma conversa de mensagens instantâneas quando o certificado expirará precisará se conectar e entrar novamente para usar o novo certificado associado ao serviço de borda de acesso. Comportamento semelhante ocorrerá para um usuário envolvido em uma conferência da Web usando o serviço de borda de Webconferência. O certificado OAuthTokenIssuer é um tipo específico compartilhado em todos os servidores. Você cria e gerencia o certificado em um local e o certificado é armazenado no repositório de gerenciamento central para todos os outros servidores.
  
Detalhes adicionais são necessários para compreender totalmente suas opções e requisitos ao usar o cmdlet Set-CsCertificate e usá-lo para dividir certificados antes do vencimento do certificado atual. O parâmetro-roll é importante, mas essencialmente propósito único. Se você defini-lo como um parâmetro, você está contando com Set-CsCertificate que você fornecerá informações sobre o certificado que será afetado definido por-tipo (por exemplo, AudioVideoAuthentication e OAuthTokenIssuer), quando o certificado será tornado efetivo definido por-EffectiveDate.
  
 **-Roll**: o parâmetro-roll é necessário e tem dependências que devem ser fornecidas juntamente com ele. Os parâmetros necessários para definir completamente quais certificados serão afetados e como eles serão aplicados:
  
 **-EffectiveDate**: o parâmetro-EffectiveDate define quando o novo certificado se tornará co-ativo com o certificado atual. O-EffectiveDate pode estar próximo do tempo de expiração do certificado atual ou pode ser um período de tempo mais longo. Um EffectiveDate mínimo recomendado para o certificado AudioVideoAuthentication seria de 8 horas, que é o tempo de vida útil do token padrão para tokens do serviço de borda de AV emitidos usando o certificado AudioVideoAuthentication.
  
Ao separar certificados OAuthTokenIssuer, há requisitos diferentes para o tempo limite antes do certificado se tornar efetivo. O tempo mínimo que o certificado OAuthTokenIssuer deve ter para este tempo limite é de 24 horas antes do tempo de vencimento do certificado atual. O tempo limite estendido para coexistência é por causa de outras funções do servidor que dependem do certificado OAuthTokenIssuer (por exemplo, Exchange Server) que possui um tempo de retenção maior para autenticação criada por certificado e materiais da chave de criptografia.
  
 **-Thumbprint**: O thumbprint é um atributo no certificado que é exclusivo para ele. O parâmetro-Thumbprint é usado para identificar o certificado que será afetado pelas ações do cmdlet Set-CsCertificate.
  
 **-Type**: o parâmetro-Type pode aceitar um tipo de uso de certificado único ou uma lista separada por vírgulas de tipos de uso de certificado. Os tipos de certificado são aqueles que identificam para o cmdlet e para o servidor qual o objetivo do certificado. Por exemplo, digite AudioVideoAuthentication é para uso pelo serviço de borda A/V e pelo serviço de autenticação de AV. Se você decidir dividir e provisionar certificados de um tipo diferente ao mesmo tempo, considere o tempo limite efetivo mínimo necessário para os certificados. Por exemplo, você precisa separar certificados do tipo AudioVideoAuthentication e OAuthTokenIssuer. O valor mínimo-EffectiveDate deve ser o maior dos dois certificados, nesse caso, o OAuthTokenIssuer, que tem um tempo de avanço mínimo de 24 horas. Se você não deseja separar o certificado AudioVideoAuthentication com um tempo limite de 24 horas, separe-o com um EffectiveDate superior aos seus requisitos.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um certificado de serviço de borda A/V com parâmetros a-roll e-EffectiveDate

1. Faça logon no computador local como membro do grupo Administradores.
    
2. Solicite uma renovação ou um novo certificado AudioVideoAuthentication com chave privada exportável para o certificado existente no serviço de borda A/V.
    
3. Importar o novo certificado AudioVideoAuthentication para o servidor de borda e todos os outros servidores de borda no pool (se você tiver um pool implantado).
    
4. Configure o certificado importado com o cmdlet Set-CsCertificate e use o parâmetro-roll com o parâmetro-EffectiveDate. A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 2:00:00 PM) menos o tempo de vida do token (por padrão, oito horas). Isso nos dá um momento em que o certificado deve ser definido como ativo e é a cadeia de \<caracteres\>EFFECTIVEDATE: "7/22/2015 6:00:00 AM". 
    
    > [!IMPORTANT]
    > Para um pool de bordas, você deve ter todos os certificados do AudioVideoAuthentication implantados e provisionados por data e hora definidos pelo parâmetro-EffectiveDate do primeiro certificado implantado para evitar possíveis interrupções nas comunicações A/V devido ao vencimento do certificado mais antigo antes que todos os tokens do cliente e do consumidor sejam renovados usando o novo certificado. 
  
    O comando Set-CsCertificate com o parâmetro-roll e-effectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Um comando Set-CsCertificate de exemplo:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > O EffectiveDate deve ser formatado para corresponder à região do seu servidor e às configurações de idioma. O exemplo usa as configurações de Idioma e Região Inglês dos EUA 
  
Para entender melhor o processo que Set-CsCertificate,-roll e-EffectiveDate usa para testar um novo certificado para emitir novos tokens AudioVideoAuthentication e ainda usar um certificado existente para validar o AudioVideoAuthentication que está em uso por consumidores, uma linha do tempo Visual é uma maneira eficaz de compreender o processo. No exemplo a seguir, o administrador determina que o certificado de serviço de borda a/V deve expirar em 2:00:00 PM no 07/22/2015. Ele solicita e recebe um novo certificado e importa-o para cada servidor de borda em seu pool. Em 2, no 07/22/2015, ele começa a executar Get-CsCertificate with-roll,-Thumbprint-Thumbprint para a cadeia de caracteres de impressão digital do novo certificado e-efetivo definido como 07/22/2015 6:00:00 AM. Ele executa esse comando em cada servidor de borda.
  
![Usar os parâmetros roll e EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Texto Explicativo**|**Estágio**|
|:-----|:-----|
|1  <br/> |Início: 22/07/2015 00:00:00  <br/> O certificado AudioVideoAuthentication atual expira 14:00:00 em 22/07/2015. Isso é determinado pelo carimbo de data/hora de vencimento no certificado. Planeje a substituição e sobreposição do certificado na conta para sobreposição de 8 horas (tempo do token padrão) antes do certificado existente atingir a hora de vencimento. O tempo limite 02:00:00 é utilizado neste exemplo para permitir que o administrador tenha tempo suficiente para colocar e provisionar os novos certificados antes da hora efetiva 06:00:00.  <br/> |
|2  <br/> |22/07/2015 02:00:00 - 22/07/2015 05:59:59  <br/> Defina certificados em servidores de borda com tempo efetivo de 6:00:00 AM (4 horas de prazo de entrega para este exemplo, mas pode ser mais longo) usando o tipo \<\> de uso de certificado Set \<-CsCertificate-Thumbprint\> impressão digital do novo \<certificado-roll-EffectiveDate DateTime String do tempo efetivo para o novo certificado\>  <br/> |
|3  <br/> |22/07/2015 06:00 - 22/07/2015 14:00  <br/> Para validar tokens, o novo certificado é usado primeiro e, se o novo certificado não conseguir validar o token, o certificado antigo será usado. Esse processo é usado para todos os tokens durante o período de sobreposição de 8 horas (tempo do token padrão).  <br/> |
|4  <br/> |Fim: 22/07/2015 14:00:01  <br/> O certificado antigo expirou e o novo certificado foi usado. O certificado antigo pode ser removido com segurança com o tipo \<\> de uso de certificado remove-CsCertificate-Type-anterior  <br/> |
   
Quando a hora efetiva é atingida (22/07/2015 06:00:00 AM), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro no novo certificado. Se a validação falhar, o certificado antigo é testado. O processo de teste do novo certificado e retorno ao certificado antigo continuará até o tempo de expiração do certificado antigo. Quando o certificado antigo vencer (22/07/2015 14:00:00 PM), os tokens serão validados apenas pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro-Previous.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um certificado do OAuthTokenIssuer com parâmetros a-roll e-EffectiveDate

1. Faça logon no computador local como membro do grupo Administradores.
    
2. Solicite uma renovação ou um novo certificado OAuthTokenIssuer com chave privada exportável para o certificado existente no servidor front-end.
    
3. Importar o novo certificado OAuthTokenIssuer para um servidor front-end no pool (se você tiver um pool implantado). O certificado OAuthTokenIssuer é replicado globalmente e apenas precisa ser atualizado ou renovado em qualquer servidor da sua implantação. O servidor front-end é usado como exemplo.
    
4. Configure o certificado importado com o cmdlet Set-CsCertificate e use o parâmetro-roll com o parâmetro-EffectiveDate. A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 2:00:00 PM) menos um mínimo de 24 horas. 
    
    O comando Set-CsCertificate com o parâmetro-roll e-effectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Um comando Set-CsCertificate de exemplo:
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> O EffectiveDate deve ser formatado para corresponder à região do seu servidor e às configurações de idioma. O exemplo usa as configurações de Idioma e Região Inglês dos EUA 
  
Quando a hora efetiva é atingida (21/07/2015 1:00:00 AM), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro no novo certificado. Se a validação falhar, o certificado antigo é testado. O processo de teste do novo certificado e retorno ao certificado antigo continuará até o tempo de expiração do certificado antigo. Quando o certificado antigo vencer (22/07/2015 14:00:00 PM), os tokens serão validados apenas pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro-Previous.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Confira também

[Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Skype for Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
