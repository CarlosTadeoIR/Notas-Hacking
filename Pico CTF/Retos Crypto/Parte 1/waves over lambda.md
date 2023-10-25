## Objetivo 

We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 39894`.

---
## Datos de acceso al nivel 

`nc jupiter.challenges.picoctf.org 39894`.

---
## Solución 

primero accedemos al servidor 

``` bash
nc jupiter.challenges.picoctf.org 39894
```

una ves dentro nos arrojara el siguiente mensaje y después nos sacara 

```bash
-------------------------------------------------------------------------------
pzcwknjv ieke mv tzgk xfnw - xkeagecpt_mv_p_zoek_fnlbrn_nwxfpwjtge
-------------------------------------------------------------------------------
bejqeec gv jieke qnv, nv m inoe nfkenrt vnmr vzleqieke, jie bzcr zx jie ven. bevmrev izfrmcw zgk ienkjv jzwejiek jikzgwi fzcw dekmzrv zx vednknjmzc, mj inr jie exxepj zx lnhmcw gv jzfekncj zx enpi zjiek'v tnkcvncr eoec pzcompjmzcv. jie fnqtekjie bevj zx zfr xeffzqvinr, bepngve zx imv lnct tenkv ncr lnct omkjgev, jie zcft pgvimzc zc reph, ncr qnv ftmcw zc jie zcft kgw. jie nppzgcjncj inr bkzgwij zgj nfkenrt n bzu zx rzlmczev, ncr qnv jztmcw nkpimjepjgknfft qmji jie bzcev. lnkfzq vnj pkzvv-fewwer kmwij nxj, fencmcw nwnmcvj jie lmssec-lnvj. ie inr vgchec pieehv, n teffzq pzldfeumzc, n vjknmwij bnph, nc nvpejmp nvdepj, ncr, qmji imv nklv rkzdder, jie dnflv zx incrv zgjqnkrv, kevelbfer nc mrzf. jie rmkepjzk, vnjmvxmer jie ncpizk inr wzzr izfr, lnre imv qnt nxj ncr vnj rzqc nlzcwvj gv. qe eupincwer n xeq qzkrv fnsmft. nxjekqnkrv jieke qnv vmfecpe zc bznkr jie tnpij. xzk vzle kenvzc zk zjiek qe rmr czj bewmc jinj wnle zx rzlmczev. qe xefj lermjnjmoe, ncr xmj xzk czjimcw bgj dfnpmr vjnkmcw. jie rnt qnv ecrmcw mc n vekecmjt zx vjmff ncr euagmvmje bkmffmncpe. jie qnjek vizce dnpmxmpnfft; jie vht, qmjizgj n vdeph, qnv n becmwc mllecvmjt zx gcvjnmcer fmwij; jie oekt lmvj zc jie evveu lnkvi qnv fmhe n wngst ncr knrmncj xnbkmp, igcw xkzl jie qzzrer kmvev mcfncr, ncr rkndmcw jie fzq vizkev mc rmndinczgv xzfrv. zcft jie wfzzl jz jie qevj, bkzzrmcw zoek jie gddek kenpiev, bepnle lzke vzlbke eoekt lmcgje, nv mx ncweker bt jie nddkznpi zx jie vgc.
```

para descifrar el mensaje tenemos que ir a la pagina https://www.guballa.de/substitution-solver y pegar todo el texto, al final lo que nos importa estará al principio
```
-------------------------------------------------------------------------------
congrats here is your flag - frequency_is_c_over_lambda_agflcgtyue
-------------------------------------------------------------------------------
```

**Resultado Final**
en este caso la bandera no llevara el típico formato de picoCTF{xxxxx}
```
frequency_is_c_over_lambda_agflcgtyue
```

---
## Notas Adicionales 

---
## Referencias 