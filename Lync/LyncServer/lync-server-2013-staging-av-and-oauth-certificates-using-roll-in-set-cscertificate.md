---
title: Como preparar certificados AV e OAuth usando o-roll in Set-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4acdf759181dee3df872c7803ec595c63fb07016
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Preparando certificados do AV e do OAuth no Lync Server 2013 usando-roll no set-CsCertificate

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-13_

As comunicações de áudio/vídeo (A/V) são um componente chave do Microsoft Lync Server 2013. Recursos como compartilhamento de aplicativos e áudio e videoconferências dependem dos certificados atribuídos ao serviço de borda a/V, especificamente para o serviço de autenticação A/V.

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>Este novo recurso foi projetado para funcionar para o serviço de borda a/V e para o certificado <EM>OAuthTokenIssuer</EM> . Outros tipos de certificados podem ser provisionados juntamente com o serviço de borda A/V e o tipo de certificado OAuth, mas não se beneficiarão do comportamento de coexistência que o certificado de serviço de borda A/V usará.</P>
> <LI>
> <P>Os cmdlets do PowerShell do Shell de gerenciamento do Lync Server usadas para gerenciar certificados do Microsoft Lync Server 2013 referem-se ao certificado de serviço de borda A/V como o tipo de certificado <EM>AudioVideoAuthentication</EM> e o certificado OAuthServer como tipo <EM> OAuthTokenIssuer</EM>. Para o restante deste tópico e para identificar exclusivamente os certificados, eles serão referidos pelo mesmo tipo de identificador, <EM>AudioVideoAuthentication</EM> e <EM>OAuthTokenIssuer</EM>.</P></LI></OL>



</div>

O serviço de Autenticação A/V é responsável por emitir tokens que são usados por clientes e outros consumidores A/V. Os tokens são gerados de atributos no certificado e, quando o certificado expira, a perda de conexão e o requisito para participar novamente com um novo token gerado pelo novo certificado resultará. Um novo recurso do Lync Server 2013 aliviará esse problema – a capacidade de testar um novo certificado antes do antigo expirar e permitir que os dois certificados continuem a funcionar por um período de tempo. Esse recurso usa a funcionalidade atualizada no cmdlet Set-CsCertificate do Shell de gerenciamento do Lync Server. O novo parâmetro –Roll, com o parâmetro existente –EffectiveDate, substituirá o novo certificado AudioVideoAuthentication no repositório de certificados. O certificado AudioVideoAuthentication mais antigo permanecerá para tokens emitidos serem validados. Começando a colocar o novo certificado AudioVideoAuthentication, a seguinte série de eventos ocorrerá:

<div>


> [!TIP]
> Usando os cmdlets do Shell de gerenciamento do Lync Server para gerenciar certificados, você pode solicitar certificados separados e distintos para cada finalidade no servidor de borda. Usar o assistente de certificado no assistente de implantação do Lync Server ajuda você a criar certificados, mas geralmente é do tipo <STRONG>padrão</STRONG> que associa todos os usos de certificado para o servidor de borda em um único certificado. A prática recomendada se você usar o recurso de agrupamento de certificado é desagrupar o certificado AudioVideoAuthentication de outros objetivos. É possível provisionar e dividir um certificado do tipo Padrão, mas apenas a parte do AudioVideoAuthentication do certificado combinado será beneficiada da separação. Um usuário envolvido (por exemplo) uma conversa de mensagens instantâneas quando o certificado expirará precisará se conectar e entrar novamente para usar o novo certificado associado ao serviço de borda de acesso. Comportamento semelhante ocorrerá para um usuário envolvido em uma conferência da Web usando o serviço de borda de Webconferência. O certificado OAuthTokenIssuer é um tipo específico compartilhado em todos os servidores. Você cria e gerencia o certificado em um local e o certificado é armazenado no repositório de gerenciamento central para todos os outros servidores.



</div>

Detalhes adicionais são necessários para compreender totalmente suas opções e requisitos ao usar o cmdlet Set-CsCertificate e usá-lo para dividir certificados antes do vencimento do certificado atual. O parâmetro –Roll é importante, mas tem essencialmente um único objetivo. Se você defini-lo como um parâmetro, está dizendo ao Set-CsCertificate que você irá fornecer informações sobre o certificado que será afetado definido pelo –Type (por exemplo, AudioVideoAuthentication e OAuthTokenIssuer), quando o certificado se tornar efetivamente definido por -EffectiveDate

**-Roll:** O parâmetro – roll é necessário e tem dependências que devem ser fornecidas juntamente com ele. Os parâmetros necessários para definir completamente quais certificados serão afetados e como eles serão aplicados:

**-EffectiveDate:** O parâmetro – EffectiveDate define quando o novo certificado se tornará co-ativo com o certificado atual. O -EffectiveDate pode estar próximo do prazo de vencimento do certificado atual ou pode ser um período de tempo mais longo. Um -EffectiveDate mínimo recomendado para o certificado AudioVideoAuthentication seria de 8 horas, que é o tempo do token padrão para os tokens de serviço de Borda AV emitidos por meio do certificado AudioVideoAuthentication.

Ao separar certificados OAuthTokenIssuer, há requisitos diferentes para o tempo limite antes do certificado se tornar efetivo. O tempo mínimo que o certificado OAuthTokenIssuer deve ter para este tempo limite é de 24 horas antes do tempo de vencimento do certificado atual. O tempo limite estendido para coexistência é por causa de outras funções do servidor que dependem do certificado OAuthTokenIssuer (por exemplo, Exchange Server) que possui um tempo de retenção maior para autenticação criada por certificado e materiais da chave de criptografia.

**-Impressão digital:** A impressão digital é um atributo do certificado exclusivo para esse certificado. O parâmetro –Thumbprint é usado para identificar o certificado que será afetado pelas ações do cmdlet Set-CsCertificate.

**-Digite:** O parâmetro – tipo pode aceitar um tipo de uso de certificado único ou uma lista separada por vírgulas de tipos de uso de certificado. Os tipos de certificado são aqueles que identificam para o cmdlet e para o servidor qual o objetivo do certificado. Por exemplo, digite AudioVideoAuthentication é para uso pelo serviço de borda A/V e pelo serviço de autenticação de AV. Se você decidir dividir e provisionar certificados de um tipo diferente ao mesmo tempo, considere o tempo limite efetivo mínimo necessário para os certificados. Por exemplo, você precisa separar certificados do tipo AudioVideoAuthentication e OAuthTokenIssuer. Seu -EffectiveDate mínimo deve ser maior que os dois certificados, neste caso o OAuthTokenIssuer, que possui um tempo limite mínimo de 24 horas. Se você não deseja separar o certificado AudioVideoAuthentication com um tempo limite de 24 horas, separe-o com um EffectiveDate superior aos seus requisitos.

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um certificado de serviço de borda A/V com parâmetros-roll e-EffectiveDate

1.  Faça logon no computador local como membro do grupo Administradores.

2.  Solicite uma renovação ou um novo certificado AudioVideoAuthentication com chave privada exportável para o certificado existente no serviço de borda A/V.

3.  Importar o novo certificado AudioVideoAuthentication para o servidor de borda e todos os outros servidores de borda no pool (se você tiver um pool implantado).

4.  Configurar o certificado importado com o cmdlet Set-CsCertificate e usar o parâmetro –Roll com o parâmetro –EffectiveDate. A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 2:00:00 PM) menos o tempo de vida do token (por padrão, oito horas). Isso nos dá um momento em que o certificado deve ser definido como ativo e é a cadeia de \<caracteres\>– EFFECTIVEDATE: "7/22/2012 6:00:00 AM".
    
    <div>
    

    > [!IMPORTANT]
    > Para um pool de bordas, você deve ter todos os certificados do AudioVideoAuthentication implantados e provisionados pela data e hora definidas pelo parâmetro – EffectiveDate do primeiro certificado implantado para evitar possíveis interrupções nas comunicações A/V devido ao mais antigo o certificado expira antes que todos os tokens do cliente e do consumidor tenham sido renovados usando o novo certificado.

    
    </div>
    
    O comando Set-CsCertificate com o parâmetro –Roll e –EffectiveTime:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Um comando Set-CsCertificate de exemplo:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > O EffectiveDate deve ser formatado para corresponder às configurações de idioma e região do seu servidor. O exemplo usa as configurações de Idioma e Região Inglês dos EUA

    
    </div>

Para compreender ainda mais o processo que o Set-CsCertificate, -Roll e –EffectiveDate usam para dividir um novo certificado para emissão de novos tokens AudioVideoAuthentication enquanto ainda usa um certificado existente para validar o AudioVideoAuthentication que está em uso por consumidores, um prazo visual é um meio eficaz de compreender o processo.

No exemplo a seguir, o administrador determina que o certificado de serviço de borda a/V deve expirar em 2:00:00 PM no 07/22/2012. Ele solicita e recebe um novo certificado e importa-o para cada servidor de borda em seu pool. Em 2, no 07/22/2012, ele começa a executar Get-CsCertificate com-roll,-Thumbprint, que é igual à cadeia de caracteres de impressão digital do novo certificado e – Efetivotime definido como 07/22/2012 6:00:00 AM. Ele executa esse comando em cada servidor de borda.

![Usar os parâmetros roll e EffectiveDate.] (images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Usar os parâmetros roll e EffectiveDate.")

Quando o tempo efetivo é atingido (7/22/2012 6:00:00 AM), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro no novo certificado. Se a validação falhar, o certificado antigo é testado. O processo de teste do novo certificado e retorno ao certificado antigo continuará até o tempo de expiração do certificado antigo. Depois que o certificado antigo tiver expirado (7/22/2012 2:00:00 PM), os tokens só serão validados pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro –Previous.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um certificado do OAuthTokenIssuer com parâmetros-roll e-EffectiveDate

1.  Faça logon no computador local como membro do grupo Administradores.

2.  Solicite uma renovação ou um novo certificado OAuthTokenIssuer com chave privada exportável para o certificado existente no serviço de borda A/V.

3.  Importar o novo certificado OAuthTokenIssuer para um servidor front-end no pool (se você tiver um pool implantado). O certificado OAuthTokenIssuer é replicado globalmente e apenas precisa ser atualizado ou renovado em qualquer servidor da sua implantação. O servidor front-end é usado como exemplo.

4.  Configurar o certificado importado com o cmdlet Set-CsCertificate e usar o parâmetro –Roll com o parâmetro –EffectiveDate. A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 2:00:00 PM) menos um mínimo de 24 horas.
    
    O comando Set-CsCertificate com o parâmetro –Roll e –EffectiveTime:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Um comando Set-CsCertificate de exemplo:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > O EffectiveDate deve ser formatado para corresponder às configurações de idioma e região do seu servidor. O exemplo usa as configurações de Idioma e Região Inglês dos EUA

    
    </div>

Quando o tempo efetivo é atingido (7/21/2012 1:00:00 AM), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro no novo certificado. Se a validação falhar, o certificado antigo é testado. O processo de teste do novo certificado e retorno ao certificado antigo continuará até o tempo de expiração do certificado antigo. Depois que o certificado antigo tiver expirado (7/22/2012 2:00:00 PM), os tokens só serão validados pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro –Previous.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejar certificados do Servidor de Borda no Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Gerenciamento de aplicativos de parceiros e autenticação de servidor para servidor (OAuth) no Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[Configurar certificados de Borda para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))  
[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

