---
title: Stage AV and OAuth certificates in Skype for Business Server using -Roll in Set-CsCertificate
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Resumo: Estágio AV e certificados OAuth para Skype for Business Server.'
ms.openlocfilehash: a2586e9ebda1bae1605fd6033681b469e6731b8c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806551"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Stage AV and OAuth certificates in Skype for Business Server using -Roll in Set-CsCertificate
 
**Resumo:** Stage AV and OAuth certificates for Skype for Business Server.
  
As comunicações de áudio/vídeo (A/V) são um componente essencial do Skype for Business Server. Recursos como compartilhamento de aplicativos e conferência de áudio e vídeo dependem dos certificados atribuídos ao serviço de Borda A/V, especificamente o serviço de Autenticação A/V.
  
> [!IMPORTANT]
> Esse novo recurso foi projetado para funcionar para o serviço de Borda A/V e o certificado OAuthTokenIssuer. Outros tipos de certificado podem ser provisionados junto com o serviço de Borda A/V e o tipo de certificado OAuth, mas não se beneficiarão do comportamento de coexistência que o certificado de serviço de Borda A/V irá.
  
Os cmdlets do PowerShell do Shell de Gerenciamento do Skype for Business Server usados para gerenciar certificados do Skype for Business Server referem-se ao certificado de serviço de Borda A/V como o tipo de certificado AudioVideoAuthentication e o certificado OAuthServer como typeOAuthTokenIssuer. Para o restante deste tópico e para identificar exclusivamente os certificados, eles serão referidos pelo mesmo tipo de identificador, AudioVideoAuthentication eOAuthTokenIssuer.
  
O serviço de Autenticação A/V é responsável pela emissão de tokens usados por clientes e outros consumidores de A/V. Os tokens são gerados a partir de atributos no certificado e, quando o certificado expirar, a perda de conexão e a exigência de re-ressarcimento com um novo token gerado pelo novo certificado resultarão. Um novo recurso no Skype for Business Server aliviará esse problema- a capacidade de criar um novo certificado antes do antigo expirar e permitir que ambos os certificados continuem a funcionar por um período de tempo. Esse recurso usa a funcionalidade atualizada no cmdlet Set-CsCertificate Shell de Gerenciamento do Skype for Business Server. O novo parâmetro -Roll, com o parâmetro existente -EffectiveDate, colocará o novo certificado AudioVideoAuthentication no armazenamento de certificados. O certificado AudioVideoAuthentication mais antigo ainda permanecerá para tokens emitidos para serem validados. A partir da colocação do novo certificado AudioVideoAuthentication, ocorrerá a seguinte série de eventos:
  
> [!TIP]
> Usando os cmdlets do Shell de Gerenciamento do Skype for Business Server para gerenciar certificados, você pode solicitar certificados separados e distintos para cada finalidade no Servidor de Borda. Usar o Assistente de Certificado no Assistente de Implantação do Skype for Business  Server ajuda você na criação de certificados, mas normalmente é do tipo padrão que faz com que todos os certificados usem para o Servidor de Borda em um único certificado. A prática recomendada se você for usar o recurso de certificado de rolagem é desafocar o certificado AudioVideoAuthentication de outras finalidades de certificado. Você pode provisionar e estágios um certificado do tipo Padrão, mas somente a parte AudioVideoAuthentication do certificado combinado se beneficiará da preparação. Um usuário envolvido em (por exemplo) uma conversa de mensagens instantâneas quando o certificado expirar precisará sair e fazer logoff novamente para usar o novo certificado associado ao serviço de Borda de Acesso. Ocorrerá um comportamento semelhante para um usuário envolvido em uma webconferência usando o serviço de Borda de Webconferência. O certificado OAuthTokenIssuer é um tipo específico compartilhado em todos os servidores. Você cria e gerencia o certificado em um só lugar e o certificado é armazenado no armazenamento de Gerenciamento Central para todos os outros servidores.
  
Detalhes adicionais são necessários para compreender totalmente suas opções e requisitos ao usar o cmdlet Set-CsCertificate e usá-lo para estágios de certificados antes da expiração atual do certificado. O parâmetro -Roll é importante, mas essencialmente uma única finalidade. Se defini-lo como um parâmetro, você estará informando Set-CsCertificate que fornecerá informações sobre o certificado que será afetado definido por -Type (por exemplo, AudioVideoAuthentication e OAuthTokenIssuer), quando o certificado se tornará efetivo definido por -EffectiveDate.
  
 **-Roll**: o parâmetro -Roll é necessário e tem dependências que devem ser fornecidas junto com ele. Parâmetros necessários para definir totalmente quais certificados serão afetados e como eles serão aplicados:
  
 **-EffectiveDate**: o parâmetro -EffectiveDate define quando o novo certificado se tornará co-ativo com o certificado atual. O -EffectiveDate pode estar perto do tempo de expiração do certificado atual ou pode ser um período de tempo mais longo. Um -EffectiveDate mínimo recomendado para o certificado AudioVideoAuthentication seria de 8 horas, que é o tempo de vida do token padrão para tokens de serviço de Borda AV emitidos usando o certificado AudioVideoAuthentication.
  
Durante a preparação de certificados OAuthTokenIssuer, há requisitos diferentes para o tempo de entrega antes que o certificado possa se tornar eficaz. O tempo mínimo que o certificado OAuthTokenIssuer deve ter para seu tempo de entrega é de 24 horas antes do tempo de expiração do certificado atual. O tempo de entrega estendido para a coexistência é devido a outras funções de servidor que dependem do certificado OAuthTokenIssuer (Exchange Server, por exemplo), que tem um tempo de retenção maior para os materiais de chave de criptografia e autenticação criados por certificados.
  
 **-Thumbprint**: a impressão digital é um atributo no certificado que é exclusivo para esse certificado. O parâmetro -Thumbprint é usado para identificar o certificado que será afetado pelas ações do Set-CsCertificate cmdlet.
  
 **-Type:** o parâmetro -Type pode aceitar um único tipo de uso de certificado ou uma lista separada por vírgulas de tipos de uso de certificado. Os tipos de certificado são aqueles que identificam para o cmdlet e para o servidor qual é a finalidade do certificado. Por exemplo, o tipo AudioVideoAuthentication deve ser usado pelo serviço de Borda A/V e pelo serviço de Autenticação AV. Se você decidir estágio e provisionar certificados de um tipo diferente ao mesmo tempo, deverá considerar o tempo de entrega mínimo mínimo necessário para os certificados. Por exemplo, você precisa estágio certificados do tipo AudioVideoAuthentication e OAuthTokenIssuer. O -EffectiveDate mínimo deve ser o maior dos dois certificados, nesse caso, o OAuthTokenIssuer, que tem um prazo mínimo de 24 horas. Se você não quiser separar o certificado AudioVideoAuthentication com um prazo de 24 horas, estágio-lo separadamente com um EffectiveDate que seja mais para seus requisitos.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um certificado de serviço de Borda A/V com parâmetros -Roll e -EffectiveDate

1. Faça logoff no computador local como membro do grupo Administradores.
    
2. Solicite uma renovação ou um novo certificado AudioVideoAuthentication com chave privada exportável para o certificado existente no serviço de Borda A/V.
    
3. Importe o novo certificado AudioVideoAuthentication para o Servidor de Borda e todos os outros Servidores de Borda em seu pool (se você tiver um pool implantado).
    
4. Configure o certificado importado com o cmdlet Set-CsCertificate e use o parâmetro -Roll com o parâmetro -EffectiveDate. A data efetiva deve ser definida como a hora de expiração do certificado atual (14:00:00 ou 14:00:00 PM) menos tempo de vida do token (por padrão, oito horas). Isso nos dá um tempo em que o certificado deve ser definido como ativo e é -EffectiveDate \<string\> : "22/7/2015 6:00:00 AM". 
    
    > [!IMPORTANT]
    > Para um pool de Borda, você deve ter todos os certificados AudioVideoAuthentication implantados e provisionados pela data e hora definidas pelo parâmetro -EffectiveDate do primeiro certificado implantado para evitar possíveis interrupções nas comunicações A/V devido à expiração do certificado mais antigo antes que todos os tokens de cliente e consumidor tenham sido renovados usando o novo certificado. 
  
    O Set-CsCertificate comando com o parâmetro -Roll e -EffectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Um exemplo Set-CsCertificate comando:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate deve ser formatado para corresponder às configurações de região e idioma do seu servidor. O exemplo usa as configurações de idioma e região inglês dos EUA 
  
Para entender ainda mais o processo que Set-CsCertificate, -Roll e -EffectiveDate usam para configurar um novo certificado para emissão de novos tokens AudioVideoAuthentication enquanto ainda usa um certificado existente para validar AudioVideoAuthentication que estão em uso pelos consumidores, uma linha do tempo visual é um meio eficaz de entender o processo. No exemplo a seguir, o administrador determina que o certificado do serviço de Borda A/V deve expirar às 14:00 em 22/07/2015. Ele solicita e recebe um novo certificado e o importa para cada Servidor de Borda em seu pool. Às 2h do dia 22/07/2015, ele começa a executar o Get-CsCertificate com -Roll, -Thumbprint igual à cadeia de impressão digital do novo certificado e -EffectiveTime definido como 22/07/2015 6:00:00 AM. Ele executa este comando em cada Servidor de Borda.
  
![Usando os parâmetros Roll e EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**Stage**|
|:-----|:-----|
|1   <br/> |Início: 22/07/2015 12:00:00  <br/> O certificado AudioVideoAuthentication atual deve expirar às 14:00 em 22/07/2015. Isso é determinado pelo carimbo de data/hora expira no certificado. Planeje a substituição e a sobreposição de certificados para levar em conta uma sobreposição de 8 horas (tempo de vida do token padrão) antes que o certificado existente atinja a hora de expiração. O prazo 2:00:00 é usado neste exemplo para permitir que o administrador coloque e provisione os novos certificados antes da hora efetiva das 6:00:00.  <br/> |
|2   <br/> |22/7/2015 02:00:00 - 22/07/2015 05:59:59  <br/> Definir certificados em Servidores de Borda com tempo efetivo de 6:00:00 (o prazo de 4 horas é para este exemplo, mas pode ser mais longo) usando Set-CsCertificate -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate \<datetime string of the effective time for new certificate\>  <br/> |
|3   <br/> |22/07/2015 06:00 - 22/07/2015 14:00  <br/> Para validar tokens, o novo certificado é experimentado primeiro e, se o novo certificado não validar o token, o certificado antigo é experimentado. Esse processo é usado para todos os tokens durante o período de sobreposição de 8 horas (tempo de vida do token padrão).  <br/> |
|4   <br/> |Término: 22/07/2015 14:00:01  <br/> O certificado antigo expirou e o novo certificado foi assumido. O certificado antigo pode ser removido com segurança Remove-CsCertificate -Type \<certificate usage type\> -Previous  <br/> |
   
Quando a hora efetiva é atingida (22/7/2015 6:00:00 AM), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro no novo certificado. Se a validação falhar, o certificado antigo será experimentado. O processo de tentar o novo e retornar ao certificado antigo continuará até o tempo de expiração do certificado antigo. Depois que o certificado antigo expirar (22/07/2015 14:00:00), os tokens só serão validados pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro -Previous.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um certificado OAuthTokenIssuer com parâmetros -Roll e -EffectiveDate

1. Faça logoff no computador local como membro do grupo Administradores.
    
2. Solicite uma renovação ou um novo certificado OAuthTokenIssuer com chave privada exportável para o certificado existente no Servidor Front-End.
    
3. Importe o novo certificado OAuthTokenIssuer para um Servidor Front End em seu pool (se você tiver um pool implantado). O certificado OAuthTokenIssuer é replicado globalmente e só precisa ser atualizado e renovado em qualquer servidor em sua implantação. O Servidor front-end é usado como exemplo.
    
4. Configure o certificado importado com o cmdlet Set-CsCertificate e use o parâmetro -Roll com o parâmetro -EffectiveDate. A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 14:00:00) menos um mínimo de 24 horas. 
    
    O Set-CsCertificate comando com o parâmetro -Roll e -EffectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Um exemplo Set-CsCertificate comando:
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> EffectiveDate deve ser formatado para corresponder às configurações de região e idioma do seu servidor. O exemplo usa as configurações de idioma e região inglês dos EUA 
  
Quando a hora efetiva é atingida (21/07/2015 1:00:00 AM), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro no novo certificado. Se a validação falhar, o certificado antigo será experimentado. O processo de tentar o novo e retornar ao certificado antigo continuará até o tempo de expiração do certificado antigo. Depois que o certificado antigo expirar (22/07/2015 14:00:00), os tokens só serão validados pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro -Previous.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Confira também

[Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Skype for Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
