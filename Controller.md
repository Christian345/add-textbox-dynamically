# add-textbox-dynamically
add-textbox dynamically in asp.net mvc
Otranzao le code le code any @contrôleur

     // GET: /Description/Create
        public ActionResult Create()
        {
            var activite = new[] {
            new ACTIVITES_POSTE { ACTIVITE_PRINCIPALES = "" },
            };
            ViewBag.activite = activite;
            return View();
        }
      
      // POST: /Description/Create
        [HttpPost]
        public ActionResult Create(DESCRIPTION description, IEnumerable<ACTIVITES_POSTE> activites)//null foana le activites eto
        {
            if (ModelState.IsValid)
            {
                db.DESCRIPTION.Add(description);
                ACTIVITES_POSTE activite = new ACTIVITES_POSTE();
                var activ = Request["activites"];//nandramako ndray otrn zao fa nul foana le izy. Tsy hitako ny fomba hi-recupérena anleh //texte
                activite.ACTIVITE_PRINCIPALES = activ;
                db.ACTIVITES_POSTE.Add(activite);
                db.SaveChanges();
                return RedirectToAction("Index");  
            }
            return View(description);
        }
        
