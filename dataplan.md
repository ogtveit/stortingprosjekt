# Notes on avaliable data and API

fra: http://data.stortinget.no/no/eksport/

~~~~
stortingsperioder [stortingsperiode.id:2017-2021][.fra/til]
sesjoner [sesjon.id:2017-2018][.fra/.til]
emner [emne.id:5][.navn:ARBEIDSLIV][.underemne.id/navn]
fylker [fylke.id:AA][navn:Aust-Agder]
partier(SesjonId) [parti.id:A][navn:Arbeiderpartiet]
allepartier [parti.id:A][navn:Arbeiderpartiet]
komiteer(SesjonId) [id:ARBSOS][navn:Arbeids....]
allekomiteer [komite.id:ARBSOS][navn:Arbeids....]
representanter(stortingsperiodeid) [representant.id:ADA][.navn:AndreOktayDahl][.fylke.][.parti.id/navn]
dagensrepresentanter [dagensrepresentant.id:SHAR][.navn:Svein..][.fylke.][.parti.id/navn][.komiteer_liste.komite]
personbilde(personid=SMY&storrelse=middels) 
sporretimesporsmal(sesjonsid) [error on line 1]
interpellasjoner(sesjonsid) [spoersmal_liste.spoersmal.tittel/spoersmal_fra/spoersmal_til/besvart_av]
skriftligesporsmal(sesjonid) [spoersmal_liste.spoersmal.tittel/spoersmal_fra/spoersmal_til/besvart_av]
saker(sesjonid) [saker_liste.sak.tittel]
sak(sakid) [detaljert_sak.innstillingstekst/.publikasjon_referanse_liste]
saksganger [saksgang_liste.saksgang.id/.navn/.saksgang_steg_liste]
voteringer(sakid)
voteringsforslag(voteringid)
voteringsvedtak(voteringid)
voteringsresultat(voteringid)
moter(sesjonid) [moter_oversikt.moter_liste.mote.][.id/.merknad/.mote_dato_tid/.referat_id]
dagsorden(moteid) [dagsordensak.dagsordensak_tekst/.sak_id]
horinger(sesjonid) 
horingsprogram(horingid)
publikasjoner(publikasjonstype (referat) & sesjonid) [publikasjoner_oversikt.publikasjoner_liste.publikasjon.dato/.id/.tittel]
publikasjon(publikasjonsid) [forhandling.mote.formalia.president/.saker.sak.sakshode/.innlegg.navn/.a (kan være flere a-er)]
~~~~

# improvement
bruke ".encode('utf-8')" før lagre fil?

# use case
data fetched with this script have been used to train a recurrent neural network (with [torch-rnn](https://github.com/jcjohnson/torch-rnn)) on [amazon aws](https://gist.github.com/lipsumar/eb55918d522f6c7f727de648e17b1d22).
to work with torch-rnn data were recoded to utf-8 manually.
