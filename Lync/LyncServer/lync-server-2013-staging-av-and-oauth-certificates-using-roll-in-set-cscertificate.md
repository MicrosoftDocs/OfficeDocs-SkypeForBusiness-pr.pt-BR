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

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a><span data-ttu-id="2ca21-102">Preparando certificados do AV e do OAuth no Lync Server 2013 usando-roll no set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="2ca21-102">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ca21-103">_**Tópico da última modificação:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="2ca21-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="2ca21-104">As comunicações de áudio/vídeo (A/V) são um componente chave do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ca21-104">Audio/Video (A/V) communications is a key component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="2ca21-105">Recursos como compartilhamento de aplicativos e áudio e videoconferências dependem dos certificados atribuídos ao serviço de borda a/V, especificamente para o serviço de autenticação A/V.</span><span class="sxs-lookup"><span data-stu-id="2ca21-105">Features such as application sharing and audio and video conferencing rely on the certificates assigned to the A/V Edge service, specifically the A/V Authentication service.</span></span>

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P><span data-ttu-id="2ca21-106">Este novo recurso foi projetado para funcionar para o serviço de borda a/V e para o certificado <EM>OAuthTokenIssuer</EM> .</span><span class="sxs-lookup"><span data-stu-id="2ca21-106">This new feature is designed to work for the A/V Edge service and the <EM>OAuthTokenIssuer</EM> certificate.</span></span> <span data-ttu-id="2ca21-107">Outros tipos de certificados podem ser provisionados juntamente com o serviço de borda A/V e o tipo de certificado OAuth, mas não se beneficiarão do comportamento de coexistência que o certificado de serviço de borda A/V usará.</span><span class="sxs-lookup"><span data-stu-id="2ca21-107">Other certificate types can be provisioned along with the A/V Edge service and OAuth certificate type, but will not benefit from the coexistence behavior that the A/V Edge service certificate will.</span></span></P>
> <LI>
> <P><span data-ttu-id="2ca21-108">Os cmdlets do PowerShell do Shell de gerenciamento do Lync Server usadas para gerenciar certificados do Microsoft Lync Server 2013 referem-se ao certificado de serviço de borda A/V como o tipo de certificado <EM>AudioVideoAuthentication</EM> e o certificado OAuthServer como tipo <EM> OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="2ca21-108">The Lync Server Management Shell PowerShell cmdlets used to manage Microsoft Lync Server 2013 certificates refers to the A/V Edge service certificate as the <EM>AudioVideoAuthentication</EM> certificate type and the OAuthServer certificate as type <EM>OAuthTokenIssuer</EM>.</span></span> <span data-ttu-id="2ca21-109">Para o restante deste tópico e para identificar exclusivamente os certificados, eles serão referidos pelo mesmo tipo de identificador, <EM>AudioVideoAuthentication</EM> e <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="2ca21-109">For the rest of this topic and to uniquely identify the certificates, they will be referred to by the same identifier type, <EM>AudioVideoAuthentication</EM> and <EM>OAuthTokenIssuer</EM>.</span></span></P></LI></OL>



</div>

<span data-ttu-id="2ca21-110">O serviço de Autenticação A/V é responsável por emitir tokens que são usados por clientes e outros consumidores A/V.</span><span class="sxs-lookup"><span data-stu-id="2ca21-110">The A/V Authentication service is responsible for issuing tokens that are used by clients and other A/V consumers.</span></span> <span data-ttu-id="2ca21-111">Os tokens são gerados de atributos no certificado e, quando o certificado expira, a perda de conexão e o requisito para participar novamente com um novo token gerado pelo novo certificado resultará.</span><span class="sxs-lookup"><span data-stu-id="2ca21-111">The tokens are generated from attributes on the certificate, and when the certificate expires, loss of connection and requirement to rejoin with a new token generated by the new certificate will result.</span></span> <span data-ttu-id="2ca21-112">Um novo recurso do Lync Server 2013 aliviará esse problema – a capacidade de testar um novo certificado antes do antigo expirar e permitir que os dois certificados continuem a funcionar por um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="2ca21-112">A new feature in Lync Server 2013 will alleviate this problem – the ability to stage a new certificate in advance of the old one expiring and allowing both certificates to continue to function for a period of time.</span></span> <span data-ttu-id="2ca21-113">Esse recurso usa a funcionalidade atualizada no cmdlet Set-CsCertificate do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ca21-113">This feature uses updated functionality in the Set-CsCertificate Lync Server Management Shell cmdlet.</span></span> <span data-ttu-id="2ca21-114">O novo parâmetro –Roll, com o parâmetro existente –EffectiveDate, substituirá o novo certificado AudioVideoAuthentication no repositório de certificados.</span><span class="sxs-lookup"><span data-stu-id="2ca21-114">The new parameter –Roll, with the existing parameter –EffectiveDate, will place the new AudioVideoAuthentication certificate in the certificate store.</span></span> <span data-ttu-id="2ca21-115">O certificado AudioVideoAuthentication mais antigo permanecerá para tokens emitidos serem validados.</span><span class="sxs-lookup"><span data-stu-id="2ca21-115">The older AudioVideoAuthentication certificate will still remain for issued tokens to be validated against.</span></span> <span data-ttu-id="2ca21-116">Começando a colocar o novo certificado AudioVideoAuthentication, a seguinte série de eventos ocorrerá:</span><span class="sxs-lookup"><span data-stu-id="2ca21-116">Beginning with putting the new AudioVideoAuthentication certificate in place, the following series of events will occur:</span></span>

<div>


> [!TIP]
> <span data-ttu-id="2ca21-117">Usando os cmdlets do Shell de gerenciamento do Lync Server para gerenciar certificados, você pode solicitar certificados separados e distintos para cada finalidade no servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="2ca21-117">Using the Lync Server Management Shell cmdlets for managing certificates, you can request separate and distinct certificates for each purpose on the Edge Server.</span></span> <span data-ttu-id="2ca21-118">Usar o assistente de certificado no assistente de implantação do Lync Server ajuda você a criar certificados, mas geralmente é do tipo <STRONG>padrão</STRONG> que associa todos os usos de certificado para o servidor de borda em um único certificado.</span><span class="sxs-lookup"><span data-stu-id="2ca21-118">Using the Certificate Wizard in the Lync Server Deployment Wizard assists you in creating certificates, but is typically of the <STRONG>default</STRONG> type which couples all certificate uses for the Edge Server onto a single certificate.</span></span> <span data-ttu-id="2ca21-119">A prática recomendada se você usar o recurso de agrupamento de certificado é desagrupar o certificado AudioVideoAuthentication de outros objetivos.</span><span class="sxs-lookup"><span data-stu-id="2ca21-119">The recommended practice if you are going to use the rolling certificate feature is to decouple the AudioVideoAuthentication certificate from the other certificate purposes.</span></span> <span data-ttu-id="2ca21-120">É possível provisionar e dividir um certificado do tipo Padrão, mas apenas a parte do AudioVideoAuthentication do certificado combinado será beneficiada da separação.</span><span class="sxs-lookup"><span data-stu-id="2ca21-120">You can provision and stage a certificate of the Default type, but only the AudioVideoAuthentication portion of the combined certificate will benefit from the staging.</span></span> <span data-ttu-id="2ca21-121">Um usuário envolvido (por exemplo) uma conversa de mensagens instantâneas quando o certificado expirará precisará se conectar e entrar novamente para usar o novo certificado associado ao serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="2ca21-121">A user involved in (for example) an instant messaging conversation when the certificate expires will need to log out and log back in to make use of the new certificate associated with the Access Edge service.</span></span> <span data-ttu-id="2ca21-122">Comportamento semelhante ocorrerá para um usuário envolvido em uma conferência da Web usando o serviço de borda de Webconferência.</span><span class="sxs-lookup"><span data-stu-id="2ca21-122">Similar behavior will occur for a user involved in a Web conference using the Web Conferencing Edge service.</span></span> <span data-ttu-id="2ca21-123">O certificado OAuthTokenIssuer é um tipo específico compartilhado em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="2ca21-123">The OAuthTokenIssuer certificate is a specific type that is shared across all servers.</span></span> <span data-ttu-id="2ca21-124">Você cria e gerencia o certificado em um local e o certificado é armazenado no repositório de gerenciamento central para todos os outros servidores.</span><span class="sxs-lookup"><span data-stu-id="2ca21-124">You create and manage the certificate in one place and the certificate is stored in the Central Management store for all other servers.</span></span>



</div>

<span data-ttu-id="2ca21-p106">Detalhes adicionais são necessários para compreender totalmente suas opções e requisitos ao usar o cmdlet Set-CsCertificate e usá-lo para dividir certificados antes do vencimento do certificado atual. O parâmetro –Roll é importante, mas tem essencialmente um único objetivo. Se você defini-lo como um parâmetro, está dizendo ao Set-CsCertificate que você irá fornecer informações sobre o certificado que será afetado definido pelo –Type (por exemplo, AudioVideoAuthentication e OAuthTokenIssuer), quando o certificado se tornar efetivamente definido por -EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="2ca21-p106">Additional detail is needed to fully understand your options and requirements when using the Set-CsCertificate cmdlet and using it to stage certificates prior to the current certificate expiring. The –Roll parameter is important, but essentially single purpose. If you define it as a parameter, you are telling Set-CsCertificate that you will be providing information about the certificate that will be affected defined by –Type (for example AudioVideoAuthentication and OAuthTokenIssuer), when the certificate will become effective defined by –EffectiveDate.</span></span>

<span data-ttu-id="2ca21-128">**-Roll:** O parâmetro – roll é necessário e tem dependências que devem ser fornecidas juntamente com ele.</span><span class="sxs-lookup"><span data-stu-id="2ca21-128">**-Roll:** The –Roll parameter is required and has dependencies that must be supplied along with it.</span></span> <span data-ttu-id="2ca21-129">Os parâmetros necessários para definir completamente quais certificados serão afetados e como eles serão aplicados:</span><span class="sxs-lookup"><span data-stu-id="2ca21-129">Required parameters to fully define which certificates will be affected and how they will be applied:</span></span>

<span data-ttu-id="2ca21-130">**-EffectiveDate:** O parâmetro – EffectiveDate define quando o novo certificado se tornará co-ativo com o certificado atual.</span><span class="sxs-lookup"><span data-stu-id="2ca21-130">**-EffectiveDate:** The parameter –EffectiveDate defines when the new certificate will become co-active with the current certificate.</span></span> <span data-ttu-id="2ca21-131">O -EffectiveDate pode estar próximo do prazo de vencimento do certificado atual ou pode ser um período de tempo mais longo.</span><span class="sxs-lookup"><span data-stu-id="2ca21-131">The –EffectiveDate can be close to the expiry time of the current certificate, or it can be a longer period of time.</span></span> <span data-ttu-id="2ca21-132">Um -EffectiveDate mínimo recomendado para o certificado AudioVideoAuthentication seria de 8 horas, que é o tempo do token padrão para os tokens de serviço de Borda AV emitidos por meio do certificado AudioVideoAuthentication.</span><span class="sxs-lookup"><span data-stu-id="2ca21-132">A recommended minimum –EffectiveDate for the AudioVideoAuthentication certificate would be 8 hours, which is the default token lifetime for AV Edge service tokens issued using the AudioVideoAuthentication certificate.</span></span>

<span data-ttu-id="2ca21-p109">Ao separar certificados OAuthTokenIssuer, há requisitos diferentes para o tempo limite antes do certificado se tornar efetivo. O tempo mínimo que o certificado OAuthTokenIssuer deve ter para este tempo limite é de 24 horas antes do tempo de vencimento do certificado atual. O tempo limite estendido para coexistência é por causa de outras funções do servidor que dependem do certificado OAuthTokenIssuer (por exemplo, Exchange Server) que possui um tempo de retenção maior para autenticação criada por certificado e materiais da chave de criptografia.</span><span class="sxs-lookup"><span data-stu-id="2ca21-p109">When staging OAuthTokenIssuer certificates, there are different requirements for the lead time before the certificate can become effective. The minimum time that the OAuthTokenIssuer certificate should have for its lead time is 24 hours before the expiration time of the current certificate. The extended lead time for the coexistence is because of other server roles that are dependent on the OAuthTokenIssuer certificate (Exchange Server, for example) which has a longer retention time for certificate created authentication and encryption key materials.</span></span>

<span data-ttu-id="2ca21-136">**-Impressão digital:** A impressão digital é um atributo do certificado exclusivo para esse certificado.</span><span class="sxs-lookup"><span data-stu-id="2ca21-136">**-Thumbprint:** The thumbprint is an attribute on the certificate that is unique to that certificate.</span></span> <span data-ttu-id="2ca21-137">O parâmetro –Thumbprint é usado para identificar o certificado que será afetado pelas ações do cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="2ca21-137">The –Thumbprint parameter is used to identify the certificate that will be affected by the actions of the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="2ca21-138">**-Digite:** O parâmetro – tipo pode aceitar um tipo de uso de certificado único ou uma lista separada por vírgulas de tipos de uso de certificado.</span><span class="sxs-lookup"><span data-stu-id="2ca21-138">**-Type:** The –Type parameter can accept a single certificate usage type or a comma separated list of certificate usage types.</span></span> <span data-ttu-id="2ca21-139">Os tipos de certificado são aqueles que identificam para o cmdlet e para o servidor qual o objetivo do certificado.</span><span class="sxs-lookup"><span data-stu-id="2ca21-139">The certificate types are those that identify to the cmdlet and to the server what the purpose of the certificate is.</span></span> <span data-ttu-id="2ca21-140">Por exemplo, digite AudioVideoAuthentication é para uso pelo serviço de borda A/V e pelo serviço de autenticação de AV.</span><span class="sxs-lookup"><span data-stu-id="2ca21-140">For example, type AudioVideoAuthentication is for use by the A/V Edge service and the AV Authentication service.</span></span> <span data-ttu-id="2ca21-141">Se você decidir dividir e provisionar certificados de um tipo diferente ao mesmo tempo, considere o tempo limite efetivo mínimo necessário para os certificados.</span><span class="sxs-lookup"><span data-stu-id="2ca21-141">If you decide to stage and provision certificates of a different type at the same time, you must consider the longest required minimum effective lead time for the certificates.</span></span> <span data-ttu-id="2ca21-142">Por exemplo, você precisa separar certificados do tipo AudioVideoAuthentication e OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="2ca21-142">For example, you need to stage certificates of type AudioVideoAuthentication and OAuthTokenIssuer.</span></span> <span data-ttu-id="2ca21-143">Seu -EffectiveDate mínimo deve ser maior que os dois certificados, neste caso o OAuthTokenIssuer, que possui um tempo limite mínimo de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="2ca21-143">Your minimum –EffectiveDate must be the greater of the two certificates, in this case the OAuthTokenIssuer, which has a minimum lead time of 24 hours.</span></span> <span data-ttu-id="2ca21-144">Se você não deseja separar o certificado AudioVideoAuthentication com um tempo limite de 24 horas, separe-o com um EffectiveDate superior aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="2ca21-144">If you do not want to stage the AudioVideoAuthentication certificate with a lead time of 24 hours, stage it separately with an EffectiveDate that is more to your requirements.</span></span>

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="2ca21-145">Para atualizar ou renovar um certificado de serviço de borda A/V com parâmetros-roll e-EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="2ca21-145">To update or renew an A/V Edge service certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="2ca21-146">Faça logon no computador local como membro do grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="2ca21-146">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="2ca21-147">Solicite uma renovação ou um novo certificado AudioVideoAuthentication com chave privada exportável para o certificado existente no serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="2ca21-147">Request a renewal or new AudioVideoAuthentication certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="2ca21-148">Importar o novo certificado AudioVideoAuthentication para o servidor de borda e todos os outros servidores de borda no pool (se você tiver um pool implantado).</span><span class="sxs-lookup"><span data-stu-id="2ca21-148">Import the new AudioVideoAuthentication certificate to the Edge Server and all other Edge Server in your pool (if you have a pool deployed).</span></span>

4.  <span data-ttu-id="2ca21-149">Configurar o certificado importado com o cmdlet Set-CsCertificate e usar o parâmetro –Roll com o parâmetro –EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="2ca21-149">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="2ca21-150">A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 2:00:00 PM) menos o tempo de vida do token (por padrão, oito horas).</span><span class="sxs-lookup"><span data-stu-id="2ca21-150">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus token lifetime (by default eight hours).</span></span> <span data-ttu-id="2ca21-151">Isso nos dá um momento em que o certificado deve ser definido como ativo e é a cadeia de \<caracteres\>– EFFECTIVEDATE: "7/22/2012 6:00:00 AM".</span><span class="sxs-lookup"><span data-stu-id="2ca21-151">This gives us a time that the certificate must be set to active, and is the –EffectiveDate \<string\>: “7/22/2012 6:00:00 AM”.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="2ca21-152">Para um pool de bordas, você deve ter todos os certificados do AudioVideoAuthentication implantados e provisionados pela data e hora definidas pelo parâmetro – EffectiveDate do primeiro certificado implantado para evitar possíveis interrupções nas comunicações A/V devido ao mais antigo o certificado expira antes que todos os tokens do cliente e do consumidor tenham sido renovados usando o novo certificado.</span><span class="sxs-lookup"><span data-stu-id="2ca21-152">For an Edge pool, you must have all AudioVideoAuthentication certificates deployed and provisioned by the date and time defined by the –EffectiveDate parameter of the first certificate deployed to avoid possible A/V communications disruption due to the older certificate expiring before all client and consumer tokens have been renewed using the new certificate.</span></span>

    
    </div>
    
    <span data-ttu-id="2ca21-153">O comando Set-CsCertificate com o parâmetro –Roll e –EffectiveTime:</span><span class="sxs-lookup"><span data-stu-id="2ca21-153">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="2ca21-154">Um comando Set-CsCertificate de exemplo:</span><span class="sxs-lookup"><span data-stu-id="2ca21-154">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="2ca21-p113">O EffectiveDate deve ser formatado para corresponder às configurações de idioma e região do seu servidor. O exemplo usa as configurações de Idioma e Região Inglês dos EUA</span><span class="sxs-lookup"><span data-stu-id="2ca21-p113">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="2ca21-157">Para compreender ainda mais o processo que o Set-CsCertificate, -Roll e –EffectiveDate usam para dividir um novo certificado para emissão de novos tokens AudioVideoAuthentication enquanto ainda usa um certificado existente para validar o AudioVideoAuthentication que está em uso por consumidores, um prazo visual é um meio eficaz de compreender o processo.</span><span class="sxs-lookup"><span data-stu-id="2ca21-157">To further understand the process that Set-CsCertificate, -Roll, and –EffectiveDate use to stage a new certificate for issuing new AudioVideoAuthentication tokens while still using an existing certificate to validate AudioVideoAuthentication that are in use by consumers, a visual timeline is an effective means of understanding the process.</span></span>

<span data-ttu-id="2ca21-158">No exemplo a seguir, o administrador determina que o certificado de serviço de borda a/V deve expirar em 2:00:00 PM no 07/22/2012.</span><span class="sxs-lookup"><span data-stu-id="2ca21-158">In the following example, the administrator determines that the A/V Edge service certificate is due to expire at 2:00:00 PM on 07/22/2012.</span></span> <span data-ttu-id="2ca21-159">Ele solicita e recebe um novo certificado e importa-o para cada servidor de borda em seu pool.</span><span class="sxs-lookup"><span data-stu-id="2ca21-159">He requests and receives a new certificate and imports it to each Edge Server in his pool.</span></span> <span data-ttu-id="2ca21-160">Em 2, no 07/22/2012, ele começa a executar Get-CsCertificate com-roll,-Thumbprint, que é igual à cadeia de caracteres de impressão digital do novo certificado e – Efetivotime definido como 07/22/2012 6:00:00 AM.</span><span class="sxs-lookup"><span data-stu-id="2ca21-160">At 2 AM on 07/22/2012, he begins running Get-CsCertificate with –Roll, -Thumbprint equal to the thumbprint string of the new certificate, and –EffectiveTime set to 07/22/2012 6:00:00 AM.</span></span> <span data-ttu-id="2ca21-161">Ele executa esse comando em cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="2ca21-161">He runs this command on each Edge Server.</span></span>

<span data-ttu-id="2ca21-162">![Usar os parâmetros roll e EffectiveDate.] (images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Usar os parâmetros roll e EffectiveDate.")</span><span class="sxs-lookup"><span data-stu-id="2ca21-162">![Using the Roll and the EffectiveDate parameters.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Using the Roll and the EffectiveDate parameters.")</span></span>

<span data-ttu-id="2ca21-163">Quando o tempo efetivo é atingido (7/22/2012 6:00:00 AM), todos os novos tokens são emitidos pelo novo certificado.</span><span class="sxs-lookup"><span data-stu-id="2ca21-163">When the effective time is reached (7/22/2012 6:00:00 AM), all new tokens are issued by the new certificate.</span></span> <span data-ttu-id="2ca21-164">Ao validar tokens, os tokens serão validados primeiro no novo certificado.</span><span class="sxs-lookup"><span data-stu-id="2ca21-164">When validating tokens, tokens will first be validated against the new certificate.</span></span> <span data-ttu-id="2ca21-165">Se a validação falhar, o certificado antigo é testado.</span><span class="sxs-lookup"><span data-stu-id="2ca21-165">If the validation fails, the old certificate is tried.</span></span> <span data-ttu-id="2ca21-166">O processo de teste do novo certificado e retorno ao certificado antigo continuará até o tempo de expiração do certificado antigo.</span><span class="sxs-lookup"><span data-stu-id="2ca21-166">The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate.</span></span> <span data-ttu-id="2ca21-167">Depois que o certificado antigo tiver expirado (7/22/2012 2:00:00 PM), os tokens só serão validados pelo novo certificado.</span><span class="sxs-lookup"><span data-stu-id="2ca21-167">Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate.</span></span> <span data-ttu-id="2ca21-168">O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro –Previous.</span><span class="sxs-lookup"><span data-stu-id="2ca21-168">The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="2ca21-169">Para atualizar ou renovar um certificado do OAuthTokenIssuer com parâmetros-roll e-EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="2ca21-169">To update or renew an OAuthTokenIssuer certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="2ca21-170">Faça logon no computador local como membro do grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="2ca21-170">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="2ca21-171">Solicite uma renovação ou um novo certificado OAuthTokenIssuer com chave privada exportável para o certificado existente no serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="2ca21-171">Request a renewal or new OAuthTokenIssuer certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="2ca21-172">Importar o novo certificado OAuthTokenIssuer para um servidor front-end no pool (se você tiver um pool implantado).</span><span class="sxs-lookup"><span data-stu-id="2ca21-172">Import the new OAuthTokenIssuer certificate to a Front End Server in your pool (if you have a pool deployed).</span></span> <span data-ttu-id="2ca21-173">O certificado OAuthTokenIssuer é replicado globalmente e apenas precisa ser atualizado ou renovado em qualquer servidor da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="2ca21-173">The OAuthTokenIssuer certificate is replicated globally and only needs to be updated and renewed at any server in your deployment.</span></span> <span data-ttu-id="2ca21-174">O servidor front-end é usado como exemplo.</span><span class="sxs-lookup"><span data-stu-id="2ca21-174">The Front End Server is used as an example.</span></span>

4.  <span data-ttu-id="2ca21-p117">Configurar o certificado importado com o cmdlet Set-CsCertificate e usar o parâmetro –Roll com o parâmetro –EffectiveDate. A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 2:00:00 PM) menos um mínimo de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="2ca21-p117">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter. The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus a minimum of 24 hours.</span></span>
    
    <span data-ttu-id="2ca21-177">O comando Set-CsCertificate com o parâmetro –Roll e –EffectiveTime:</span><span class="sxs-lookup"><span data-stu-id="2ca21-177">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="2ca21-178">Um comando Set-CsCertificate de exemplo:</span><span class="sxs-lookup"><span data-stu-id="2ca21-178">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="2ca21-p118">O EffectiveDate deve ser formatado para corresponder às configurações de idioma e região do seu servidor. O exemplo usa as configurações de Idioma e Região Inglês dos EUA</span><span class="sxs-lookup"><span data-stu-id="2ca21-p118">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="2ca21-181">Quando o tempo efetivo é atingido (7/21/2012 1:00:00 AM), todos os novos tokens são emitidos pelo novo certificado.</span><span class="sxs-lookup"><span data-stu-id="2ca21-181">When the effective time is reached (7/21/2012 1:00:00 AM), all new tokens are issued by the new certificate.</span></span> <span data-ttu-id="2ca21-182">Ao validar tokens, os tokens serão validados primeiro no novo certificado.</span><span class="sxs-lookup"><span data-stu-id="2ca21-182">When validating tokens, tokens will first be validated against the new certificate.</span></span> <span data-ttu-id="2ca21-183">Se a validação falhar, o certificado antigo é testado.</span><span class="sxs-lookup"><span data-stu-id="2ca21-183">If the validation fails, the old certificate is tried.</span></span> <span data-ttu-id="2ca21-184">O processo de teste do novo certificado e retorno ao certificado antigo continuará até o tempo de expiração do certificado antigo.</span><span class="sxs-lookup"><span data-stu-id="2ca21-184">The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate.</span></span> <span data-ttu-id="2ca21-185">Depois que o certificado antigo tiver expirado (7/22/2012 2:00:00 PM), os tokens só serão validados pelo novo certificado.</span><span class="sxs-lookup"><span data-stu-id="2ca21-185">Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate.</span></span> <span data-ttu-id="2ca21-186">O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro –Previous.</span><span class="sxs-lookup"><span data-stu-id="2ca21-186">The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2ca21-187">Confira também</span><span class="sxs-lookup"><span data-stu-id="2ca21-187">See Also</span></span>


[<span data-ttu-id="2ca21-188">Planejar certificados do Servidor de Borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ca21-188">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="2ca21-189">Gerenciamento de aplicativos de parceiros e autenticação de servidor para servidor (OAuth) no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ca21-189">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[<span data-ttu-id="2ca21-190">Configurar certificados de Borda para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ca21-190">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
<span data-ttu-id="2ca21-191">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ca21-191">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span></span>  
<span data-ttu-id="2ca21-192">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="2ca21-192">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

